# php-矩阵转换
将一个只含有1和0的方形矩阵上有1的行和列上的各个数字转换为1
 
举个栗子 将数组1转换成数组2

    $arr = array(
    array(0,0,1,1,0),
    array(0,0,1,0,0),
    array(0,0,0,0,0),
    array(0,0,0,0,0)
    );
    
    $arr = array(
    array(1,1,1,1,1),
    array(1,1,1,1,1),
    array(0,0,0,1,0),
    array(0,0,0,1,0)
    );

    <?php
    /**
    author:ansion
    time:2017年4月14日
    **/
    $arr = array(
        array(0,0,1,1,1),
        array(0,0,1,0,0),
        array(0,0,0,0,1),
        array(0,0,0,0,0)
        );
    //新建一个存放数字1所在位置的二维数组，键存放行号，一维数组的键存放列号
    $position = array();
        //遍历矩阵
        foreach($arr as $keys=>$values){
            foreach($values as $k=>$v){
                if($v === 1){
                    //键存放行号，一维数组的键存放列号
                    $position[$keys][$k] = 1;
                }

            }
        }
        foreach($position as $keys1=>$values1){
            //引用遍历给符合条件矩阵行赋值1
            foreach($arr[$keys1] as &$v1){
                $v1 = 1;
            }
            //引用遍历符合条件矩阵列赋值1
            foreach($values1 as $k3=>$v3){
                foreach($arr as &$v2){
                    $v2[$k3] = 1;
                }            
            }
        }
        var_dump($arr);
