# 유튜브정보


## 할당량

10,000

서치 100 씩 하루에 100번

## 

요청
HTTP 요청

GET https://www.googleapis.com/youtube/v3/search
매개변수
다음 표에는 이 쿼리가 지원하는 매개변수가 나와 있습니다. 나열된 모든 매개변수는 쿼리 매개변수입니다.

매개변수
필수 매개변수
part	string
part 매개변수는 API 응답이 포함하는 search 리소스 속성 하나 이상의 쉼표로 구분된 목록을 지정합니다. 매개변수 값을 snippet로 설정합니다.
필터(다음 매개변수 중 0개 또는 1개 지정)
forContentOwner	boolean
이 매개변수는 제대로 인증된 요청에서만 사용할 수 있으며 YouTube 콘텐츠 파트너 전용입니다.

forContentOwner 매개변수는 onBehalfOfContentOwner 매개변수로 식별된 콘텐츠 소유자가 소유한 동영상만 가져오도록 검색을 제한합니다. forContentOwner가 true로 설정된 경우 요청은 다음 요구사항도 충족해야 합니다.
onBehalfOfContentOwner 매개변수는 필수 항목입니다.
요청을 승인하는 사용자는 지정된 콘텐츠 소유자와 연결된 계정을 사용해야 합니다.
type 매개변수 값은 video로 설정해야 합니다.
videoDefinition, videoDimension, videoDuration, videoEmbeddable, videoLicense, videoPaidProductPlacement, videoSyndicated, videoType의 다른 매개변수는 설정할 수 없습니다.
forDeveloper	boolean
이 매개변수는 제대로 승인된 요청에서만 사용할 수 있습니다. forDeveloper 매개변수는 개발자의 애플리케이션 또는 웹사이트를 통해 업로드된 동영상만 가져오도록 검색을 제한합니다. API 서버는 요청의 승인 사용자 인증 정보를 사용하여 개발자를 식별합니다. forDeveloper 매개변수는 q 매개변수와 같은 선택적 검색 매개변수와 함께 사용할 수 있습니다.

이 기능을 위해 업로드된 각 동영상은 Google Developers Console에서 개발자의 애플리케이션과 연결된 프로젝트 번호로 자동으로 태그가 지정됩니다.

이후 검색 요청에서 forDeveloper 매개변수를 true로 설정하면 API 서버는 요청의 승인 사용자 인증 정보를 사용하여 개발자를 식별합니다. 따라서 개발자는 검색 결과를 개발자의 앱 또는 웹사이트를 통해 업로드된 동영상으로 제한할 수 있지만 다른 앱이나 사이트를 통해 업로드된 동영상으로는 제한할 수 없습니다.
forMine	boolean
이 매개변수는 제대로 승인된 요청에서만 사용할 수 있습니다. forMine 매개변수는 인증된 사용자가 소유한 동영상만 검색하도록 검색을 제한합니다. 이 매개변수를 true로 설정하는 경우 type 매개변수의 값도 video로 설정해야 합니다. 또한 동일한 요청에서 videoDefinition, videoDimension, videoDuration, videoEmbeddable, videoLicense, videoPaidProductPlacement, videoSyndicated, videoType의 다른 매개변수를 설정할 수 없습니다.
선택적 매개변수
channelId	string
channelId 매개변수는 API 응답이 채널에서 만든 리소스만 포함해야 함을 나타냅니다.

참고: 요청에서 channelId 매개변수의 값을 지정하고 type 매개변수 값을 video로 설정하지만 forContentOwner, forDeveloper 또는 forMine 필터 중 하나를 설정하지 않은 경우 검색결과가 최대 500개의 동영상으로 제한됩니다.
channelType	string
channelType 매개변수를 사용하면 특정 유형의 채널로 검색을 제한할 수 있습니다.

허용되는 값은 다음과 같습니다.
any – 모든 채널을 반환합니다.
show – 프로그램만 검색합니다.
eventType	string
eventType 매개변수는 브로드캐스트 이벤트로 검색을 제한합니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
completed – 완료된 브로드캐스트만 포함합니다.
live – 활성 브로드캐스트만 포함합니다.
upcoming – 예정된 브로드캐스트만 포함합니다.
location	string
location 매개변수는 locationRadius 매개변수와 함께 원형의 지리적 영역을 정의하며, 메타데이터에서 해당 지역에 속하는 지리적 위치를 지정하는 동영상으로 검색을 제한합니다. 매개변수 값은 위도/경도 좌표를 지정하는 문자열입니다(예: (37.42307,-122.08427)).

location 매개변수 값은 영역의 중심에 있는 점을 식별합니다.
locationRadius 매개변수는 동영상이 검색결과에 계속 포함될 수 있는 해당 지점부터 동영상과 연결된 위치가 있을 수 있는 최대 거리를 지정합니다.
요청이 location 매개변수의 값을 지정하지만 locationRadius 매개변수의 값을 지정하지 않는 경우 API는 오류를 반환합니다.

참고: 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.
locationRadius	string
locationRadius 매개변수는 location 매개변수와 함께 원형의 지리적 영역을 정의합니다.

매개변수 값은 부동 소수점 숫자 뒤에 측정 단위가 와야 합니다. 유효한 측정 단위는 m, km, ft, mi입니다. 예를 들어 유효한 매개변수 값에는 1500m, 5km, 10000ft, 0.75mi이 있습니다. API는 1,000킬로미터를 초과하는 locationRadius 매개변수 값을 지원하지 않습니다.

참고: 자세한 내용은 location 매개변수의 정의를 참고하세요.
maxResults	unsigned integer
maxResults 매개변수는 결과 집합에 반환해야 하는 최대 항목 수를 지정합니다. 사용 가능한 값: 0~50 기본값은 5입니다.
onBehalfOfContentOwner	string
이 매개변수는 제대로 승인된 요청에서만 사용할 수 있습니다. 참고: 이 매개변수는 YouTube 콘텐츠 파트너 전용입니다.

onBehalfOfContentOwner 매개변수는 요청의 승인 사용자 인증 정보가 매개변수 값에 지정된 콘텐츠 소유자를 대신하는 YouTube CMS 사용자를 식별함을 나타냅니다. 이 매개변수는 다양한 YouTube 채널을 소유하고 관리하는 YouTube 콘텐츠 파트너를 위한 것입니다. 콘텐츠 소유자가 각 채널에 사용자 인증 정보를 제공하지 않고도 한 번만 인증하면 모든 동영상 및 채널 데이터에 액세스할 수 있습니다. 사용자가 인증할 CMS 계정은 지정된 YouTube 콘텐츠 소유자에게 연결되어야 합니다.
order	string
order 매개변수는 API 응답에서 리소스를 정렬하는 데 사용할 메서드를 지정합니다. 기본값은 relevance입니다.

허용되는 값은 다음과 같습니다.
date – 리소스를 만든 날짜를 기준으로 최근 항목부터 시간 순서대로 리소스를 정렬합니다.
rating – 높은 평점에서 낮은 평점순으로 리소스가 정렬됩니다.
relevance – 검색어와의 관련성을 기준으로 리소스를 정렬합니다. 이 매개변수의 기본값입니다.
title – 제목에 따라 알파벳순으로 리소스를 정렬합니다.
videoCount – 업로드된 동영상 수에 따라 채널을 내림차순으로 정렬합니다.
viewCount – 리소스가 조회수가 높은 순에서 낮은 순으로 정렬됩니다. 실시간 방송의 경우 방송이 진행되는 동안 동시 시청자 수를 기준으로 동영상이 정렬됩니다.
pageToken	string
pageToken 매개변수는 반환해야 하는 결과 집합의 특정 페이지를 식별합니다. API 응답에서 nextPageToken 속성과 prevPageToken 속성은 검색 가능한 다른 페이지를 식별합니다.
publishedAfter	datetime
publishedAfter 매개변수는 API 응답이 지정된 시간 또는 그 이후에 생성된 리소스만 포함해야 함을 나타냅니다. 값은 RFC 3339 형식이 지정된 날짜-시간 값(1970-01-01T00:00:00Z)입니다.
publishedBefore	datetime
publishedBefore 매개변수는 API 응답이 지정된 시간에 만들어진 리소스만 포함해야 함을 나타냅니다. 값은 RFC 3339 형식이 지정된 날짜-시간 값(1970-01-01T00:00:00Z)입니다.
q	string
q 매개변수는 검색할 검색어를 지정합니다.

요청에서 부울 NOT (-) 및 OR (|) 연산자를 사용하여 동영상을 제외하거나 여러 검색어 중 하나와 연결된 동영상을 찾을 수도 있습니다. 예를 들어 '보트' 또는 '항해'와 일치하는 동영상을 검색하려면 q 매개변수 값을 boating|sailing로 설정합니다. 마찬가지로 '보트' 또는 '항해'와 일치하지만 '낚시'와는 일치하지 않는 동영상을 검색하려면 q 매개변수 값을 boating|sailing -fishing로 설정합니다. 파이프 문자는 API 요청에서 전송될 때 URL 이스케이프 처리되어야 합니다. 파이프 문자의 URL 이스케이프 값은 %7C입니다.
regionCode	string
regionCode 매개변수는 지정된 국가에서 볼 수 있는 동영상의 검색결과를 반환하도록 API에 지시합니다. 매개변수 값은 ISO 3166-1 alpha-2 국가 코드입니다.
relevanceLanguage	string
relevanceLanguage 매개변수는 지정된 언어와 가장 관련성이 높은 검색결과를 반환하도록 API에 지시합니다. 매개변수 값은 일반적으로 ISO 639-1 두 자리 언어 코드입니다. 하지만 중국어 간체에는 zh-Hans 값을, 중국어 번체에는 zh-Hant 값을 사용해야 합니다. 검색어와 관련성이 높은 다른 언어의 검색결과도 표시됩니다.
safeSearch	string
safeSearch 매개변수는 검색결과에 표준 콘텐츠뿐 아니라 제한된 콘텐츠도 포함되는지 여부를 나타냅니다.

허용되는 값은 다음과 같습니다.
moderate – YouTube가 검색 결과에서 일부 콘텐츠를 필터링하며 최소한 사용자 언어로 제한된 콘텐츠는 필터링합니다. 콘텐츠를 기준으로 검색결과에서 검색결과를 제거할 수도 있고 순위를 내릴 수도 있습니다. 기본 매개변수 값입니다.
none – YouTube가 검색결과 집합을 필터링하지 않습니다.
strict - YouTube가 검색결과 집합에서 제한된 콘텐츠를 모두 제외합니다. 콘텐츠를 기준으로 검색결과에서 검색결과를 제거할 수도 있고 순위를 내릴 수도 있습니다.
topicId	string
topicId 매개변수는 API 응답에 지정된 주제와 연결된 리소스만 포함해야 함을 나타냅니다. 이 값은 Freebase 주제 ID를 식별합니다.

중요: Freebase 및 Freebase API의 지원 중단으로 인해 2017년 2월 27일부터 topicId 매개변수가 다르게 작동하기 시작했습니다. 당시 YouTube는 선별된 주제 ID 중 일부를 지원하기 시작했기 때문에 이 매개변수의 값으로는 이렇게 소수의 ID만 사용할 수 있습니다.

2017년 2월 15일부터 지원되는 주제 ID 보기
type	string
type 매개변수는 특정 유형의 리소스만 검색하도록 검색어를 제한합니다. 값은 쉼표로 구분된 리소스 유형 목록입니다. 기본값은 video,channel,playlist입니다.

허용되는 값은 다음과 같습니다.
channel
playlist
video
videoCaption	string
videoCaption 매개변수는 자막이 있는지에 따라 API가 동영상 검색결과를 필터링해야 하는지 여부를 나타냅니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any - 자막 사용 가능 여부에 따라 결과를 필터링하지 않습니다.
closedCaption – 캡션이 있는 동영상만 포함합니다.
none – 자막이 없는 동영상만 포함합니다.
videoCategoryId	string
videoCategoryId 매개변수는 카테고리를 기준으로 동영상 검색결과를 필터링합니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.
videoDefinition	string
videoDefinition 매개변수를 사용하면 고화질 (HD) 또는 표준 화질 (SD) 동영상만 포함하도록 검색을 제한할 수 있습니다. HD 동영상은 최소 720p로 재생할 수 있고 1080p 같은 고해상도도 사용할 수 있습니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any - 해상도에 관계없이 모든 동영상을 반환합니다.
high – HD 동영상만 검색합니다.
standard – 표준 화질 동영상만 검색합니다.
videoDimension	string
videoDimension 매개변수를 사용하면 2D 또는 3D 동영상만 검색하도록 검색을 제한할 수 있습니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
2d – 3D 동영상을 제외하도록 검색결과를 제한합니다.
3d – 3D 동영상만 포함하도록 검색결과를 제한합니다.
any - 반환된 결과에 3D 동영상과 3D가 아닌 동영상을 모두 포함합니다. 기본값입니다.
videoDuration	string
videoDuration 매개변수는 동영상 길이를 기준으로 동영상 검색결과를 필터링합니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any – 동영상 길이를 기준으로 동영상 검색결과를 필터링하지 않습니다. 기본값입니다.
long – 20분보다 긴 동영상만 포함합니다.
medium – 4분 이상 20분 이하인 동영상만 포함합니다.
short – 4분 미만인 동영상만 포함합니다.
videoEmbeddable	string
videoEmbeddable 매개변수를 사용하면 웹페이지에 삽입할 수 있는 동영상으로만 검색을 제한할 수 있습니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any – 퍼갈 수 있는지 여부에 관계없이 모든 동영상을 반환합니다.
true – 퍼갈 수 있는 동영상만 검색합니다.
videoLicense	string
videoLicense 매개변수는 특정 라이선스가 있는 동영상만 포함하도록 검색결과를 필터링합니다. YouTube에서는 동영상 업로더가 각 동영상에 Creative Commons 라이선스 또는 표준 YouTube 라이선스를 첨부하도록 선택할 수 있습니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any - 소유한 라이선스에 관계없이 쿼리 매개변수와 일치하는 모든 동영상을 반환합니다.
creativeCommon – 크리에이티브 커먼즈 라이선스가 있는 동영상만 반환합니다. 사용자는 자신이 만든 다른 동영상에서 이 라이선스를 사용한 동영상을 재사용할 수 있습니다. 자세히 알아보기
youtube – 표준 YouTube 라이선스가 있는 동영상만 반환합니다.
videoPaidProductPlacement	string
videoPaidProductPlacement 매개변수는 크리에이터가 유료 프로모션이 있다고 표시한 동영상만 포함하도록 검색결과를 필터링합니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any – 유료 프로모션이 포함되었는지 여부와 관계없이 모든 동영상을 반환합니다.
true – 유료 프로모션이 있는 동영상만 검색합니다.
videoSyndicated	string
videoSyndicated 매개변수를 사용하면 youtube.com 외부에서 재생할 수 있는 동영상으로만 검색을 제한할 수 있습니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any – 배급 여부에 관계없이 모든 동영상을 반환합니다.
true – 배급된 동영상만 검색합니다.
videoType	string
videoType 매개변수를 사용하면 특정 유형의 동영상으로 검색을 제한할 수 있습니다. 이 매개변수의 값을 지정하는 경우 type 매개변수의 값도 video로 설정해야 합니다.

허용되는 값은 다음과 같습니다.
any – 모든 동영상을 반환합니다.
episode – 프로그램의 에피소드만 검색합니다.
movie – 영화만 검색합니다.