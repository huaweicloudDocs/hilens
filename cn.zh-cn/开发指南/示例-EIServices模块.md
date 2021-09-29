# 示例-EIServices模块<a name="hilens_05_0059"></a>

EIServices模块输出示例代码如下：

```
import hilens
import cv2
import numpy as np
import base64
import json

def run():
    # 使用图片作为输入
    f=open('/tmp/dengchao.jpg','rb')
    base_f=base64.b64encode(f.read())
    f_string=base_f.decode('utf-8')
    



    # 使用Mat格式或者直接从摄像头输入
    #img = cv2.imread("/tmp/dengchao.jpg")
    cap = hilens.VideoCapture()
    frame = cap.read()
    img = cv2.cvtColor(frame, cv2.COLOR_YUV2BGR_NV21)
    img_str = cv2.imencode('.jpg', img)[1].tostring()  # 将图片编码成流数据，放到内存缓存中，然后转化成string格式
    b64_code = base64.b64encode(img_str) # 编码成base64
    f_string1=b64_code.decode('utf-8')
    



    headers = hilens.EIHeaders()
    body = {"image_base64": f_string}
    json_str = json.dumps(body)
    response5 = hilens.EIServices.Request(hilens.POST, "hilens-api.cn-north-4.myhuaweicloud.com", "/v1/human-detect", "", json_str, headers)
    print(response5.requestState)
    print(response5.responseBody)
    body1 = {"face_set_name": "ei_test"}
    json_str1 = json.dumps(body1)
    response6 = hilens.EIServices.Request(hilens.POST, "face.cn-north-4.myhuaweicloud.com", "/v1/fc3bc995e9c441369d71159c67404e88/face-sets", "", json_str1, headers)
    print(response6.requestState)
    print(response6.responseBody)
    response7 = hilens.EIServices.AddFace("ei_test", f_string, "")
    print(response7.requestState)
    print(response7.responseBody)
    response8 = hilens.EIServices.SearchFace("ei_test", f_string, 1, 0.93, "")
    print(response8.requestState)
    print(response8.responseBody)
    response9 = hilens.EIServices.Request(hilens.POST, "face.cn-north-4.myhuaweicloud.com","/v1/fc3bc995e9c441369d71159c67404e88/face-sets/ei_test/search", "", json_str, headers)
    print(response9.requestState)
    print(response9.responseBody)
    response10 = hilens.EIServices.Request(hilens.DELETE, "face.cn-north-4.myhuaweicloud.com", "/v1/fc3bc995e9c441369d71159c67404e88/face-sets/ei_test", "", "", headers)
    print(response10.requestState)
    print(response10.responseBody)
    response11 = hilens.EIServices.Request(hilens.GET, "face.cn-north-4.myhuaweicloud.com", "/v1/fc3bc995e9c441369d71159c67404e88/face-sets/ei_test", "", "", headers)
    print(response11.requestState)
    print(response11.responseBody)

if __name__ == '__main__':
    hilens.init("hello")
    run()
    hilens.terminate()
```

