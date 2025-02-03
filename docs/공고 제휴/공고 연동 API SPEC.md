# 공고 연동 API SPEC

<!-- 제휴사의 공고를 가져와 직행이 연동을 하기 위해,   -->
<!-- api 엔드포인트를 만들어줘야합니다. -->

<!-- api 엔드포인트 예시입니다. -->

<!-- > <mark style="color:green;">**`GET`**</mark> `<AFFILIATE_COMPANY_API_URL>/api/affiliate/zighang/recruitment`&#x20; -->

<!-- 제휴사에서 연동 api 작업이 완료되면   -->
<!-- 직행팀  (`paca@zighang.com` ) 및 개발부서와 소통한 뒤,   -->
<!-- 연동이 완료됩니다. -->

<br>

<!-- 해당 api는 다음 Request, Response 스펙을 만족하도록 만들어져야 합니다. -->

<!-- ## Request Format

<mark style="color:red;">**`*`**</mark>  표시는 필수입니다.

| Field Name                             | Type                             | Description                             | Allowed Values                                                                                                                                                                                                                                  |
| -------------------------------------- | -------------------------------- | --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sort                                   | String                           | Sort criteria                           | "DEADLINE","UPLOAD"                                                                                                                                                                                                                             |
| orderBy                                | String                           | Sort order                              | "DESC","ASC"                                                                                                                                                                                                                                    |
| companyTypes                           | List\<String>                    | Company types                           | "STARTUP","MAJOR","UNICORN","MIDDLE\_MARKET","PUBLIC","ETC","FOREIGN","PUBLIC\_INSTITUTION","SMALL\_MARKET"                                                                                                                                     |
| recruitmentTypes                       | List\<String>                    | Recruitment types                       | "CONVERTIBLE\_INTERN","FULL\_TIME","CONTRACT","INDUSTRIAL\_TECHNICAL","PROFESSIONAL\_RESEARCH","OPEN\_RECRUITMENT","OCCASIONAL\_RECRUITMENT","DAY\_WORKER","EXPERIENTIAL\_INTERN"                                                               |
| educations                             | List\<String>                    | <p>Education</p><p>requirements</p>     | "IRRELEVANCE","HIGH\_SCHOOL","BACHELOR","MASTER","DOCTOR","JUNIOR\_COLLEGE"                                                                                                                                                                     |
| years                                  | <p>List&#x3C;Integer</p><p>></p> | <p>Required</p><p>experience</p>        | 0 \~ 99 (IRRELEVANCE: -1)                                                                                                                                                                                                                       |
| regions                                | List\<String>                    | <p>Recruitment</p><p>locations</p>      | "SEOUL","GYEONGGI","INCHEON","BUSAN","DAEGU","GWANGJU","DAEJEON","ULSAN","SEJONG","GANGWON","GYEONGNAM","GYEONGBUK","JEONNAM","JEONBUK","CHUNGNAM","CHUNGBUK","JEJU","ETC"                                                                      |
| deadlineTypes                          | List\<String>                    | Deadline types                          | "ALL\_TIME","CLOSE\_WHEN\_RECRUITMENT","DUE\_DATE","EXPIRED"                                                                                                                                                                                    |
| industries                             | String                           | <p>Industry</p><p>classification</p>    | "MEDICAL\_PHARMACEUTICAL\_WELFARE","MANUFACTURING\_CHEMICAL","SALES\_DISTRIBUTION","IT\_WEB\_COMMUNICATION","CONSTRUCTION","EDUCATION","MEDIA\_DESIGN","BANKING\_FINANCIAL","INSTITUTIONS\_ASSOCIATIONS","SERVICE","ETC","AGRICULTURE","MINING" |
| createdDateMin                         | Interger                         | <p>Created date</p><p>minimum</p>       | 1727050583611 (milliseconds since epoch)                                                                                                                                                                                                        |
| createdDateMax                         | Interger                         | <p>Created date</p><p>maximum</p>       | 1727050583611 (milliseconds since epoch)                                                                                                                                                                                                        |
| workStartDate                          | Interger                         | Work start date                         | 1727050583611 (milliseconds since epoch)                                                                                                                                                                                                        |
| workEndDate                            | Interger                         | Work end date                           | 1727050583611 (milliseconds since epoch)                                                                                                                                                                                                        |
| <p>lastModifiedDate</p><p>Min</p>      | Interger                         | <p>Last modified date</p><p>minimum</p> | 1727050583611 (milliseconds since epoch)                                                                                                                                                                                                        |
| <p>lastModifiedDate</p><p>Max</p>      | Integer                          | <p>Last modified date</p><p>maximum</p> | 1727050583611 (milliseconds since epoch)                                                                                                                                                                                                        |
| page<mark style="color:red;">\*</mark> | Integer                          | Limit                                   | -                                                                                                                                                                                                                                               |
| size<mark style="color:red;">\*</mark> | Integer                          | Offset                                  | 1 \~ 100                                                                                                                                                                                                                                        |

 -->


## Response Format

| Field Name | Type | Description | Allowed Values |
|------------|------|-------------|----------------|
| recruitmentUid | String | Recruitment UID | String |
| title | String | Title | String |
| mainImageUrl | String | Main image URL | String |
| companyName | String | Company name | String |
| companyTypes | String | Company type | "STARTUP","MAJOR","UNICORN","MIDDLE_MARKET","PUBLIC","ETC","FOREIGN","PUBLIC_INSTITUTION","SMALL_MARKET" |
| industryTypes | List<String> | Industry classifications | "MEDICAL_PHARMACEUTICAL_WELFARE","MANUFACTURING_CHEMICAL","SALES_DISTRIBUTION","IT_WEB_COMMUNICATION","CONSTRUCTION","EDUCATION","MEDIA_DESIGN","BANKING_FINANCIAL","INSTITUTIONS_ASSOCIATIONS","SERVICE","ETC","AGRICULTURE","MINING" |
| companyAddress | String | Company address | String |
| recruitmentJobs | Map<String, List<String>> | Job categories | Refer to external document |
| recruitmentAnnouncementLink | String | Announcement link | String |
| recruitmentTypes | List<String> | Recruitment types | "CONVERTIBLE_INTERN","FULL_TIME","CONTRACT","INDUSTRIAL_TECHNICAL","PROFESSIONAL_RESEARCH","OPEN_RECRUITMENT","OCCASIONAL_RECRUITMENT","DAY_WORKER","EXPERIENTIAL_INTERN" |
| educations | List<String> | Education requirements | "IRRELEVANCE","HIGH_SCHOOL","BACHELOR","MASTER","DOCTOR","JUNIOR_COLLEGE" |
| yearsMin | Integer | Year of experience requirements minimum | 0 ~ 99 (IRRELEVANCE: -1) |
| yearsMax | Integer | Year of experience requirements maximum | 0 ~ 99 (IRRELEVANCE: -1) |
| regions | List<String> | Work locations | "SEOUL","GYEONGGI","INCHEON","BUSAN","DAEGU","GWANGJU","DAEJEON","ULSAN","SEJONG","GANGWON","GYEONGNAM","GYEONGBUK","JEONNAM","JEONBUK","CHUNGNAM","CHUNGBUK","JEJU","ETC" |
| recruitmentStartDate | Integer | Recruitment start date | 1727050583611 (milliseconds since epoch) |
| workStartDate | Integer | Work start date | 1727050583611 (milliseconds since epoch) |
| workEndDate | Integer | Work end date | 1727050583611 (milliseconds since epoch) |
| createdDate | Integer | Upload date | 1727050583611 (milliseconds since epoch) |
| lastModifiedDate | Integer | Last modified date | 1727050583611 (milliseconds since epoch) |
| recruitmentDeadlineDate | Integer | Recruitment deadline | 1727050583611 (milliseconds since epoch) |
| deadlineType | String | Deadline type | "ALL_TIME","CLOSE_WHEN_RECRUITMENT","DUE_DATE","EXPIRED" |

<!-- <table><thead><tr><th width="210">Field Name</th><th>Type</th><th>Description</th><th>Allowed Values</th></tr></thead><tbody><tr><td>recruitmentUid</td><td>String</td><td>Recruitment UID</td><td>String</td></tr><tr><td>title</td><td>String</td><td>Title</td><td>String</td></tr><tr><td>mainImageUrl</td><td>String</td><td>Main image URL</td><td>String</td></tr><tr><td>companyName</td><td>String</td><td>Company name</td><td>String</td></tr><tr><td>companyTypes</td><td>String</td><td>Company type</td><td>"STARTUP","MAJOR","UNICORN","MIDDLE_MARKET","PUBLIC","ETC","FOREIGN","PUBLIC_INSTITUTION","SMALL_MARKET"</td></tr><tr><td>industryTypes</td><td>List&#x3C;String></td><td>Industry classifications</td><td>"MEDICAL_PHARMACEUTICAL_WELFARE","MANUFACTURING_CHEMICAL","SALES_DISTRIBUTION","IT_WEB_COMMUNICATION","CONSTRUCTION","EDUCATION","MEDIA_DESIGN","BANKING_FINANCIAL","INSTITUTIONS_ASSOCIATIONS","SERVICE","ETC","AGRICULTURE","MINING"</td></tr><tr><td>companyAddress</td><td>String</td><td>Company address</td><td>String</td></tr><tr><td>recruitmentJobs</td><td>Map&#x3C;String, List&#x3C;String>></td><td>Job categories</td><td>Refer to external document</td></tr><tr><td><p>recruitmentAnnou</p><p>ncementLink</p></td><td>String</td><td>Announcement link</td><td>String</td></tr><tr><td>recruitmentTypes</td><td>List&#x3C;String></td><td>Recruitment types</td><td>"CONVERTIBLE_INTERN","FULL_TIME","CONTRACT","INDUSTRIAL_TECHNICAL","PROFESSIONAL_RESEARCH","OPEN_RECRUITMENT","OCCASIONAL_RECRUITMENT","DAY_WORKER","EXPERIENTIAL_INTERN"</td></tr><tr><td>educations</td><td>List&#x3C;String></td><td>Education requirements</td><td>"IRRELEVANCE","HIGH_SCHOOL","BACHELOR","MASTER","DOCTOR","JUNIOR_COLLEGE"</td></tr><tr><td>yearsMin</td><td>Integer</td><td>Year of experience requirements minimum</td><td>0 ~ 99 (IRRELEVANCE: -1)</td></tr><tr><td>yearsMax</td><td>Integer</td><td><p>Year of</p><p>experience</p><p>requirements</p><p>maximum</p></td><td>0 ~ 99 (IRRELEVANCE: -1)</td></tr><tr><td>regions</td><td>List&#x3C;String></td><td>Work locations</td><td>"SEOUL","GYEONGGI","INCHEON","BUSAN","DAEGU","GWANGJU","DAEJEON","ULSAN","SEJONG","GANGWON","GYEONGNAM","GYEONGBUK","JEONNAM","JEONBUK","CHUNGNAM","CHUNGBUK","JEJU","ETC"</td></tr><tr><td><p>recruitmentStartD</p><p>ate</p></td><td>Integer</td><td>Recruitment start date</td><td>1727050583611 (milliseconds since epoch)</td></tr><tr><td>workStartDate</td><td>Integer</td><td>Work start date</td><td>1727050583611 (milliseconds since epoch)</td></tr><tr><td>workEndDate</td><td>Integer</td><td>Work end date</td><td>1727050583611 (milliseconds since epoch)</td></tr><tr><td>createdDate</td><td>Integer</td><td>Upload date</td><td>1727050583611 (milliseconds since epoch)</td></tr><tr><td>lastModifiedDate</td><td>Integer</td><td>Last modified date</td><td>1727050583611 (milliseconds since epoch)</td></tr><tr><td><p>recruitmentDeadli</p><p>neDate</p></td><td>Integer</td><td>Recruitment deadline</td><td>1727050583611 (milliseconds since epoch)</td></tr><tr><td>deadlineType</td><td>String</td><td>Deadline type</td><td>"ALL_TIME","CLOSE_WHEN_RECRUITMENT","DUE_DATE","EXPIRED"</td></tr></tbody></table> -->





