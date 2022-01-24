 location ~ \.php$ {
    #    root           html;
        try_files $uri $uri/ /index.php$is_args$query_string;
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
    fastcgi_pass   172.22.0.3:9000;
        fastcgi_index  index.php;
        #fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
fastcgi_param SCRIPT_FILENAME /usr/share/nginx/html$fastcgi_script_name;
include        fastcgi_params;
    }



-- với fastcgi pass 172.22.0.3:9000       - 172.22.0.3 : là địa chỉ ip container php khi join vào network

--sửa fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;
+ thành: fastcgi_param SCRIPT_FILENAME /usr/share/nginx/html$fastcgi_script_name;


-- tạo network:

+ docker network create --driver brigde tenmang
#join container vào network

+ docker network connect tenmang ten_or_id_container

