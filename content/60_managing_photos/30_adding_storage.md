+++
title = "Cloud Storage 추가하기"
chapter = false
weight = 30
+++

앨범에 업로드한 모든 사진들을 보관할 저장소가 필요합니다. Amazon Simple Storage Service (S3)는 이를 위한 좋은 서비스이기도 하고 Amplify의 스토리지 모듈을 이용하면 S3에 대한 설정과 작업이 아주 쉽습니다.

{{% notice tip %}}
Amplify 스토리지 모듈에 대해 다음 자료를 참고하세요. [here](https://aws-amplify.github.io/amplify-js/media/storage_guide).
{{% /notice %}}

### 스토리지 구성 및 추가

먼저, Amplify CLI로 어플리케이션의 스토리지를 활성화 합니다. 이 작업은 Amazon S3에 Bucket을 생성하고 앱에 로그인한 사용자들이 버킷을 읽고 쓸수 있는 적잘한 권한을 설정해 줍니다.

1. **사진앨범 디렉토리에서 다음 명령어를 수행합니다.** `amplify add storage`

2. 명령창에서 **'Content'를 선택하세요**

3. 리소스 카테고리 및 버킷 이름에 **값을 입력하거나 기본값** 을 수락합니다.

4. **인증된 사용자 만 읽기/쓰기 권한에**. 접근할 수 있도록 설정합니다.

    응답 예시는 다음과 같습니다:

    ```text
    $ amplify add storage


    ? Please select from one of the below mentioned services: 

    Content (Images, audio, video, etc.)


    ? Please provide a friendly name for your resource that will be used to label this category in the project: 

    photoalbumsstorage


    ? Please provide bucket name: 

    <accept the default value>


    ? Who should have access: 

    Auth users only


    ? What kind of access do you want for Authenticated users: 

    read/write
    ```


Amplify는 방금 추가 한 스토리지 리소스를 프로비저닝하여 클라우드 환경을 수정하게 됩니다.

1. **다음 명령어를 실행합니다.** `amplify push` 
2. 바뀐 내용을 확인하기 위해 **Enter를 누릅니다.** 
3. 프로비저닝이 완료 될 때까지 기다립니다. 저장 용량을 추가하는 데는 보통 1-2 분 정도 소요됩니다.