php 获取批量上传图片数据
例子：
Array(
    [name] => Array
    (
        [0] => facepalm.jpg
        [1] =>
    )
    [type] => Array
    (
        [0] => image/jpeg
        [1] =>
    )
    [tmp_name] => Array
    (
        [0] => /tmp/phpn3FmFr
        [1] =>
    )
    [error] => Array
    (
        [0] => 0
        [1] => 4
    )
    [size] => Array
    (
        [0] => 15476
        [1] => 0
    )
)
结果：
Array(
    [0] => Array
    (
        [name] => facepalm.jpg
        [type] => image/jpeg
        [tmp_name] => /tmp/phpn3FmFr
        [error] => 0
        [size] => 15476
    )
    [1] => Array
    (
        [name] =>
        [type] =>
        [tmp_name] =>
        [error] => 4
        [size] =>
    )
)

function normalize_files_array($files = []) {
    $normalized_array = [];
    foreach($files as $index => $file) {
        foreach($files[$index] as $idx => $name) {
            $normalized_array[$idx]['name'] = $files['name'][$idx];
            $normalized_array[$idx]['type'] = $files['type'][$idx];
            $normalized_array[$idx]['tmp_name'] = $files['tmp_name'][$idx];
            $normalized_array[$idx]['error'] = $files['error'][$idx];
            $normalized_array[$idx]['size'] = $files['size'][$idx];
        }

    }
    return $normalized_array;
}
