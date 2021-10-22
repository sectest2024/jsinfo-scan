# jsinfo-scan
jsinfo-scan简单改版，增加了swagger、druid目录扫描和手机号、身份证号敏感信息匹配

#匹配敏感信息
'Swagger UI': r'((swagger-ui.html)|(\"swagger\":)|(Swagger UI)|(swaggerUi))',
'Druid': r'((Druid Stat Index)|(druid monitor))',
'Spring Boot': r'((local.server.port)|(:{\"mappings\":{\")|({\"_links\":{\"self\":))',
'IDCard': '[^0-9]((\d{8}(0\d|10|11|12)([0-2]\d|30|31)\d{3}$)|(\d{6}(18|19|20)\d{2}(0[1-9]|10|11|12)([0-2]\d|30|31)\d{3}(\d|X|x)))[^0-9]',
'Phone': '[^0-9A-Za-z](1(3([0-35-9]\d|4[1-8])|4[14-9]\d|5([\d]\d|7[1-79])|66\d|7[2-35-8]\d|8\d{2}|9[89]\d)\d{7})[^0-9A-Za-z]',
        
#敏感目录
vul_path = r"""
        druid/index.html
        system/index.html
        webpage/system/druid/index.html
        api
        swagger-ui.html
        swagger/ui/index
        api/swagger-ui.html
        swagger/index.html
        env
        trace
        actuator
        api/env
        api/trace
        actuator/env
        actuator/trace
        monitor/env
        gateway/actuator/env
        """
