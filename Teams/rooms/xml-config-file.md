---
title: Microsoft Teams Rooms のデバイス設定をリモートで管理する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: カスタム テーマの適用やマスター設定ファイルの作成など、Microsoft Teams Rooms デバイスで使用される既定の設定のリモート管理について説明します。
ms.openlocfilehash: 15cedb921657d9be646fcd1aef94f15f989eec4f
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761139"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>Microsoft Teams Rooms のコンソールの設定を、XML 構成ファイルを使用してリモートで管理する

この記事では、カスタム テーマの適用など、 Microsoft Teams Rooms デバイスによって使用される既定の設定のリモート管理について説明します。 マスター設定ファイルを作成する方法と、必要に応じてTeams Roomsに配置する方法に関する説明へのリンクについて説明します。
  
マスター XML ファイルを更新し、リモート Teams Rooms デバイスにコピーを送信することで、Teams Roomsの既定の設定を変更できます。 
  
## <a name="create-an-xml-configuration-file"></a>XML 構成ファイルを作成する

任意のテキスト エディターを使用して、設定ファイルを作成できます。 **XML要素** の表に、サンプルの SkypeSettings.xml （必須のファイル名） 構成ファイルに含まれる要素を説明します。
  
```XML
<SkypeSettings>
  <AutoScreenShare>1</AutoScreenShare>
  <HideMeetingName>1</HideMeetingName>
  <AutoExitMeetingEnabled>true</AutoExitMeetingEnabled>
  <AudioRenderDefaultDeviceVolume>70</AudioRenderDefaultDeviceVolume>
  <AudioRenderCommunicationDeviceVolume>30</AudioRenderCommunicationDeviceVolume>
  <UserAccount>
    <SkypeSignInAddress>username@microsoft.com</SkypeSignInAddress>
    <ExchangeAddress>username@microsoft.com</ExchangeAddress>
    <DomainUsername>domain\username</DomainUsername>
    <Password>Password!</Password>
    <ConfigureDomain>domain1, domain2</ConfigureDomain>
    <ModernAuthEnabled>true</ModernAuthEnabled>
  </UserAccount>
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
  <SfbMeetingEnabled>true</SfbMeetingEnabled>
  <IsTeamsDefaultClient>true</IsTeamsDefaultClient>
  <WebExMeetingsEnabled>true</WebExMeetingsEnabled>
  <ZoomMeetingsEnabled>true</ZoomMeetingsEnabled>
  <UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>
  <CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>
  <CustomDisplayEmailForThirdPartyMeetings>guest@microsoft.com</CustomDisplayEmailForThirdPartyMeetings>
  <BluetoothAdvertisementEnabled>false</BluetoothAdvertisementEnabled>
  <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
  <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
  <DualScreenMode>0</DualScreenMode>
  <DuplicateIngestDefault>true</DuplicateIngestDefault>
  <DisableTeamsAudioSharing>true</DisableTeamsAudioSharing>
  <FrontRowEnabled>true</FrontRowEnabled>
  <DefaultFoRExperience>0</DefaultFoRExperience>
  <EnablePublicPreview>false</EnablePublicPreview>
  <NoiseSuppressionDefault>0</NoiseSuppressionDefault>
  <SendLogs>
    <EmailAddressForLogsAndFeedback>username@microsoft.com</EmailAddressForLogsAndFeedback>
    <SendLogsAndFeedback>True</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
    <MicrophoneForCommunication>Device1</MicrophoneForCommunication>
    <SpeakerForCommunication>DeviceX</SpeakerForCommunication>
    <DefaultSpeaker>DeviceX</DefaultSpeaker>
    <ContentCameraId>Camera1</ContentCameraId>
    <ContentCameraEnhancement>true</ContentCameraEnhancement>
    <ContentCameraInverted>false</ContentCameraInverted>
  </Devices>
  <Theming>
       <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>file name</CustomThemeImageUrl>
       <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
       </CustomThemeColor>
  </Theming>
  <CoordinatedMeetings enabled="true">
    <TrustedAccounts>username1@microsoft.com,username2@contoso.com</TrustedAccounts>
    <Settings>
      <Audio default="true" enabled="true"/>
      <Video default="true" enabled="true"/>
      <Whiteboard default="true" enabled="true"/>
    </Settings>
  </CoordinatedMeetings>
  <EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting> 
  <MainFoRDisplay> 
      <MainFoRDisplayResolution>1920,1080</MainFoRDisplayResolution> 
      <MainFoRDisplayScaling>100</MainFoRDisplayScaling> 
  </MainFoRDisplay> 
  <ExtendedFoRDisplay> 
      <ExtendedFoRDisplayResolution>1920,1080</ExtendedFoRDisplayResolution> 
      <ExtendedFoRDisplayScaling>100</ExtendedFoRDisplayScaling> 
  </ExtendedFoRDisplay>  
</SkypeSettings>
```

変数の型の値が間違っている、要素が順番に表示されていない、要素が閉じられていない、または別のエラーが発生した場合、XML ファイルは *形式が正しくない* 状態です。 形式が正しくない XML ファイルを処理しているときに、エラーの発生が適用される時点までの設定が検出されると、ファイルの残りの部分が無視されます。 XML 内の不明な要素は無視されます。 パラメーターは削除されると、変更されないままデバイス上に残ります。 パラメーター値が無効な場合、前の値が変更されないまま残ります。
  
**XML 要素**

| 要素                                     | 型                        | レベル          | 使用方法                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|:--------------------------------------------|:----------------------------|:---------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<SkypeSettings\>                           | すべての要素のコンテナー。 |                | 必須です。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<AutoScreenShare\>                         | ブール値 &#x2777;            | First &#x2776; | True の場合、[自動画面共有] が有効になります。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<HideMeetingName\>                         | ブール値 &#x2777;            | First &#x2776; | True の場合、会議名は非表示になります。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<UserAccount\>                             | コンテナー                   | First &#x2776; | 資格情報パラメーター用のコンテナー サインイン アドレス、Exchange アドレス、またはメールアドレスは、通常は同一のものとなります (RanierConf<span></span>@contoso.com など)。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SkypeSignInAddress\>                      | 文字列&#x2777;             |                | コンソールの SfB または Teams デバイス アカウントのサインイン名。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ExchangeAddress\>                         | 文字列  &#x2778;            |                | コンソールの Exchange デバイス アカウントのサインイン名。 ExchangeAddress が省略された場合、SkypeSignInAddress が自動的に再利用されることはありません。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<DomainUsername\>                          | 文字列&#x2777;            |                | Seattle\RanierConf. のようなコンソール デバイスのドメインおよびユーザー名。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<Password\>                                | 文字列  &#x2778;            |                | パスワード パラメーターは、Skype for Business デバイス アカウントのサインインに使用するパスワードと同じです。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ConfigureDomain\>                         | 文字列&#x2777;            |                | 複数のドメインをコンマで区切って表示することができます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<ModernAuthEnabled>                        | ブール値 &#x2777;            |                | 既定では無効になっています。 <br/> <br/>True に設定すると、Microsoft Teams Rooms アプリケーションは先進認証を使用してリソースに接続するだけで、基本認証にはフォールバックしません。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<TeamsMeetingsEnabled\>                    | ブール値 &#x2777;            | First &#x2776; | 既定では無効になっています。 <br/> <br/> \<SkypeMeetingsEnabled\>と\<TeamsMeetingsEnabled\>が無効になっている場合は、XML ファイルの形式が正しくないと考えられますが、両方の設定を同時に有効にすることができます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| \<SfbMeetingEnabled\>                       | ブール&#x2778;            | First &#x2776; | 既定では無効になっています。
| \<IsTeamsDefaultClient>                     | ブール値 &#x2777;            | First &#x2776; | 既定では有効になっています。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<WebExMeetingsEnabled\>                    | ブール値 &#x2777;            | First &#x2776; | 既定では無効になっています。 <br/> <br/> True の場合、Cisco Webex 会議に直接ゲスト参加することが可能になります。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| \<ZoomMeetingsEnabled\>                     | ブール値 &#x2777;            | First &#x2776; | 既定では無効になっています。 <br/> <br/> true の場合、Zoom 会議の直接ゲスト参加エクスペリエンスが有効になります。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<UseCustomInfoForThirdPartyMeetings\>      | ブール値 &#x2777;            | First &#x2776; | 既定では無効になっており、会議室のアカウント情報を使用してサードパーティの会議に参加します。 <br/> <br/> この値を True にすると、\<CustomDisplayNameForThirdPartyMeetings\>と\<CustomDisplayEmailForThirdPartyMeetings\>の両方を指定する必要があります。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<CustomDisplayNameForThirdPartyMeetings\>  | 文字列  &#x2778;            | First &#x2776; | サードパーティの会議に参加するには、ゲスト名を指定します。 サードパーティ サービスは、操作環境でこのデータを表示し、サービスに格納する場合があります。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CustomDisplayEmailForThirdPartyMeetings\> | 文字列  &#x2778;            | First &#x2776; | サードパーティの会議に参加するために使用するゲストのメールアドレスを指定します。 サードパーティ サービスは、操作環境でこのデータを表示し、サービスに格納する場合があります。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BluetoothAdvertisementEnabled>            | ブール値 &#x2777;            | First &#x2776; | 既定では有効になっています。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<AutoAcceptProximateMeetingInvitations>    | ブール値 &#x2777;            | First &#x2776; | True の場合は、近接性ベースの会議が自動的に承諾されます。 既定では無効になっています。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<AutoExitMeetingEnabled>                   | ブール値 &#x2777;            | First &#x2776; | true の場合、デバイスは会議に残っている最後の参加者である場合、会議を自動的に終了します。  既定では無効になっています。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<DualScreenMode\>                          | ブール値 &#x2777;            | First &#x2776; | true の場合、2 画面表示モードが有効になります。 それ以外の場合、デバイスでは 1 画面表示モードが使用されます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DuplicateIngestDefault\>                  | ブール値 &#x2777;            | First &#x2776; | True の場合、会議を終了しているときに、2 画面表示モードで両方の画面にコンテンツが表示されます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DisableTeamsAudioSharing\>                | ブール値 &#x2777;            | First &#x2776; | 会議の会議参加者に対する HDMI オーディオ共有を無効にするには、true に設定Teams。 既定の設定は False です。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<FrontRowEnabled>                          | ブール値 &#x2777;            | First &#x2776; | 既定では有効になっています。 false の場合、フロント行は無効になります。
| \<DefaultFoRExperience>                     | ブール値 &#x2777;            | First &#x2776; | 既定ではギャラリー ビュー。 既定のレイアウトをギャラリー ビューからフロント 行に変更するには、1 を配置します。
| \<EnablePublicPreview\>                     | ブール値 &#x2777;            | First &#x2776; | 既定では無効になっています。 true の場合、パブリック プレビューが有効になり、エンド ユーザーは有効なTeams Roomsのパブリック プレビューの機能にアクセスできます。 詳細については、[WindowsのMicrosoft Teams Roomsのパブリック プレビュー](../public-preview-doc-updates.md#public-preview-for-microsoft-teams-rooms-on-windows)を参照してください。 |
| \<NoiseSuppressionDefault\>                 | ブール値 &#x2777;            | First &#x2776; | 既定では有効になっています。 無効にするには 0 を指定します。 無効にしてもデスクトップ設定には影響しません。これは、Teams Room アカウントにのみ適用されます。
| \<CortanaWakewordEnabled\>                  | ブール値 &#x2777;            | First &#x2776; | Cortanaウェイク ワード "Hey Cortana" を有効にするには、true に設定します。 この設定は、Cortana サービスが国または地域でサポートされ、接続されているオーディオ周辺機器がCortanaをサポートしている場合を除き、何の効果も得られません。 既定の設定は False です。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<SendLogs\>                                | コンテナー                   | First &#x2776; |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<EmailAddressForLogsAndFeedback\>          | 文字列  &#x2778;            |                | [フィードバックの送信] ウィンドウが表示されたときにログの送信先となるオプションのメールアドレスを設定します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<SendLogsAndFeedback\>                     | ブール値 &#x2777;            |                | True の場合、ログは管理者に送信されます。False の場合は、フィードバックのみが管理者に送信され、ログには送信されません。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<Devices\>                                 | コンテナー                   | First &#x2776; | 子要素内の接続済みのオーディオ デバイス名は、デバイス マネージャー アプリにリスト表示された値と同一のものになります。 この構成には、現在コンソールに接続していない A/V デバイスなど、現在システムに存在しないデバイスを含めることができます。 この構成はそれぞれのデバイスに対して保持されます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<MicrophoneForCommunication\>              | 文字列  &#x2778;            |                | 会議で録音デバイスとして使用されるマイクを設定します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SpeakerForCommunication\>                 | 文字列  &#x2778;            |                | 会議でスピーカーとして使用するデバイス。 この設定では、通話で使用するスピーカー デバイスを設定します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<DefaultSpeaker\>                          | 文字列  &#x2778;            |                | HDMI 取り込みソースからのオーディオの再生に使用するデバイス。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<ContentCameraId>                          | 文字列  &#x2778;            |                | 会議でアナログのホワイトボード コンテンツを共有するために、会議室に構成されているカメラのインスタンス パスを定義します。 詳細については、「[コンテンツ カメラの USB インスタンス パス](#locate-the-content-camera-usb-instance-path)」を参照してください。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<ContentCameraInverted>                    | ブール値 &#x2777;            |                | コンテンツ カメラが物理的に上下逆さまに設置されているかどうかを指定します。 自動回転に対応したコンテンツ カメラの場合は、False を指定します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<ContentCameraEnhancement>                 | ブール値 &#x2777;            |                | True (既定) に設定すると、コンテンツ カメラの画像はデジタル機能が強化されます。ホワイトボードの端が検出され、適切な拡大率が選択されます。インクの線が強化され、ホワイトボードに書くユーザーが透明になります。  <br><br> ホワイトボードにペンで書き込む代わりに、カメラを使って付箋、ポスターなどのメディアを表示することにスペースを活用して、会議参加者に未編集のビデオフィードを送信する場合は、False に設定します。                                                                                                                                                                                                                                                                                                                                                                                             |
| \<Theming\>                                 | コンテナー                   | First &#x2776; | XML ファイルを使用して適用できる機能の 1 つに、所属組織のカスタム テーマがあります。 テーマ名、背景画像、色を指定できます。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<ThemeName\>                               | 文字列  &#x2778;            |                | クライアントのテーマを特定するために使用されます。 テーマ名のオプションは、既定、提供されたプリセット テーマのいずれか、またはカスタムになります。 <br/>  ユーザー設定のテーマ名は常に *Custom* という名前を使います。 クライアント UI は、コンソールで、既定またはプリセットのいずれかに設定できますが、ユーザー設定のテーマの使用は管理者によってリモートで設定する必要があります。 <br/>  プリセット テーマには次のものが含まれます:  <br/>  既定値 <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  ロードマップ <br/>  終了する <br/>  現在の名前を無効にするには、ThemeName で [No Theme] を使用します。                                                                                                                                                                                                                                                                               |
| \<CustomThemeImageUrl\>                     | 文字列  &#x2778;            |                | ユーザー設定のテーマの場合は必須ですが、それ以外の場合は省略可能です。 ファイル名のみを入力します。   ユーザー設定のテーマ画像の詳細については、「[ユーザー設定のテーマ画像](xml-config-file.md#Themes)」セクションを参照してください。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<CustomThemeColor\>                        | コンテナー                   |                | \<RedComponent\>、\<GreenComponent\>、および\<BlueComponent\>値のコンテナー。 これらの値は必須ですが、テーマの色には影響しません。 0 ~ 255 の任意の値を指定してください。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<RedComponent\>                            | Byte (0-255)                |                | 赤のカラー コンポーネントを表します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<GreenComponent\>                          | Byte (0-255)                |                | 緑のカラー コンポーネントを表します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BlueComponent\>                           | Byte (0-255)                |                | 青のカラー コンポーネントを表します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CoordinatedMeetings\>                     | ブール値 &#x2777;            | First &#x2776; | 会議の最適化を構成する要素のコンテナー。 この要素は 1 つの属性を持っています。<ul><li><b>有効</b>Teams が他のデバイスとの会議の最適化に参加するように構成されているかどうかを決定します。</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<TrustedAccounts\>                         | 文字列                      |                | これは、それぞれの Teams ミーティング デバイスまたは Surface Hub 用の UPN をカンマで区切ったリストで、デバイスが会議への参加依頼を承諾するか、または送信する必要があるかを指定します。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<Settings\>                                | コンテナー                   |                | 会議を最適化するためにオーディオおよびビデオの構成要素を構成するためのコンテナー。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<Audio\>                                   | ブール値 &#x2777;            |                | Teams ミーティング デバイスでオーディオ構成を制御します。 この要素には 2 つの属性があります。<br><ul><li><b>既定</b>会議の開始時にマイクをアクティブにするデバイスを決定します。 このフィールドを`true`に設定できるのは 1 つのデバイス (通常は Teams ミーティング デバイス) のみで、残りのデバイスはオーディオのエコーやハウリングを避けるためにこのフィールドを`false`に設定しなければなりません。</li><li><b>有効</b>会議の参加者がマイクのオンとオフを切り替えられるようにするかどうかを決定します。 **オーディオの既定** が`false`に設定されているデバイスでは、参加者が誤ってマイクの電源を入れてしまい、オーディオのエコーやハウリングが発生しないように、この設定を`false`に設定しておく必要があります。<p>**オーディオの既定** が`true`に設定されている場合、**オーディオが有効** 設定は無視され、参加者はマイクをミュートにしたりミュート解除したりすることができます。</li></ul>                        |
| \<Video\>                                   | ブール値 &#x2777;            |                | Teams ミーティング デバイスのビデオ構成を制御します。 この要素には 2 つの属性があります。<br><ul><li><b>既定</b>会議の開始時にカメラをアクティブにするデバイスを決定します。 最適な操作性を実現するために、他のすべてのデバイスが`false`に設定されている間は、Teams ミーティング デバイスだけを`true`に設定することをお勧めします。</li><li><b>有効</b>会議の参加者がカメラのオンとオフを切り替えられるようにするかどうかを決定します。 参加者が、Surface Hub ホワイトボードを使用している場合など、イベント参加者が別のデバイスで`true`に設定することができるようにします。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> **ビデオの既定** が`true`に設定されている場合、**ビデオが有効** 設定は無視され、参加者はビデオのオンとオフを切り替えることができます。</li></ul> |
| \<Whiteboard\>                              | ブール値 &#x2777;            |                | Teams ミーティング デバイスのホワイトボード構成を制御します。 この要素には 2 つの属性があります。<br><ul><li><b>既定</b>会議の開始時にホワイトボードをアクティブにするデバイスを決定します。 最適な操作性を実現するために、Teams ミーティング デバイスを`false`に設定し、Surface Hub でホワイトボードを使うことをお勧めします。</li><li><b>有効</b>会議の参加者がホワイトボードのオンとオフを切り替えられるようにするかどうかを決定します。 参加者がデバイスでホワイトボードのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> **ホワイトボードの既定** が`true`に設定されている場合、**ホワイトボードが有効** 設定は無視され、参加者はホワイトボードのオンとオフを切り替えることができます。</li></ul>                                                                                                                                                   |
| \<EnableResolutionAndScalingSetting\> | ブール値 &#x2777; | First &#x2776; | 既定では無効になっています。 Front of Room の解像度とスケーリングを変更する場合は、true に設定します。 true の場合、表示の解像度とスケールの設定が適用されます。 この設定が有効になると、メイン FoR と Extended FoR の両方に影響します。 |
| \<MainFoRDisplay\> | コンテナー | | デバイスが単一表示モードを使用している場合は、このコンテナーを使用します。<br><br>デュアルディスプレイ モードでは、メイン フロント オブ ルーム (FoR) は、クロック (会議外) とセルフプレビュー ビデオ (会議中) を備えた画面です。 \<MainFoRDisplayResolution\> 一 \<MainFoRDisplayScaling\> 度に一緒に設定する必要があります。 どちらか一方\<MainFoRDisplayResolution\>\<MainFoRDisplayScaling\>のみを使用する場合は無視されます。 |
| \<MainFoRDisplayResolution\> | 文字列 | | 幅、高さ (1920,1080 など) の入力数値。 FoR でサポートされていない場合は無視されます。|
| \<MainFoRDisplayScaling\> | 数値 | | スケーリングの数値を入力します。 有効な値は 100 (推奨)、125、150、175、200、225、250、300、350、400、450、500 です。 入力が 500 で、FoR が最大 300 をサポートしている場合は、300 に設定されます。|
| \<ExtendedFoRDisplay\> | コンテナー | | デュアルディスプレイ モードでは、ルームの延長前面 (FoR) は、共有コンテンツ (会議中) を表示する画面です。  \<ExtendedFoRDisplayResolution\> 一 \<ExtendedFoRDisplayScaling\> 度に一緒に設定する必要があります。 どちらか一方\<ExtendedFoRDisplayResolution\>\<ExtendedFoRDisplayScaling\>のみを使用する場合は無視されます。 |
| \<ExtendedFoRDisplayResolution\> | 文字列 | |Width、Height (1920,1080 など) の入力数値。 FoR が値をサポートしていない場合、値は無視されます。 |
| \<ExtendedFoRDisplayScaling\> | 数値 | | スケーリングの数値を入力します。 有効な値は 100 (推奨)、125、150、175、200、225、250、300、350、400、450、500 です。 入力が 500 で、FoR が最大 300 をサポートしている場合は、300 に設定されます。 |

&#x2776; 第 1 レベルの要素はすべて省略可能です。 第 1 レベルの要素が省略されると、その子要素はすべて変更されないままデバイス上に残ります。
  
&#x2777; ブール値のフラグは、True、False、0、1 を指定できます。 ブール値や数値を空のままにしておくと、XML の形式が正しくない状態になり、設定を変更できなくなります。
  
&#x2778; 3 文字列パラメーターが存在するが空であり、かつ空が有効な値である場合、デバイス上のパラメーターがクリアされます。
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>XML 構成ファイルを使用してコンソールの設定を管理する

起動時に、Microsoft Teams Rooms コンソールが`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`にある SkypeSettings.xml という名前の XML ファイルを見つけると、XML ファイルで示される構成設定を適用し、XML ファイルを削除します。
  
所属する企業で何台の Microsoft Teams Rooms デバイスを所有しているか、およびそれらを構成するためにどのような方法を選択するかに応じて、XML 構成ファイルを配置する方法が複数あります。 ファイルがコンソールにプッシュされたら、再起動して構成の変更を処理します。 処理に成功すると、XML 構成ファイルが削除されます。 Microsoft Teams Rooms デバイスで推奨される管理方法は次のとおりです。
  
- [Microsoft Teams Rooms のグループ ポリシーを構成する](rooms-operations.md#GroupPolicy)
- [PowerShellを使用してリモート管理](rooms-operations.md#RemotePS)を行い、[ファイル アイテムを構成](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))します。

ファイルの転送と、コンソール デバイス上での再起動のトリガーができるのであれば、いずれの方法も使用できます。 ファイルは、デバイスのローカル ユーザー アカウントで読み取り、書き込み、削除が可能であることが必要です。 できれば、そのユーザーが所有し、完全な特権が与えられることがよいでしょう。 ファイルの権限が適切に設定されていない場合、ソフトウェアは設定の適用に失敗したり、処理成功時にファイルの削除に失敗する可能性があるだけではなく、クラッシュする可能性があります。
  
## <a name="supported-meeting-modes-app-version-49"></a>サポートされている会議モード アプリ バージョン 4.9

**Skype for Business (既定) および Microsoft Teams**

| XML 表記                | XML 値      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>     |   True         |
| \<SfbMeetingEnabled>        |   True         |
| \<IsTeamsDefaultClient>     |   False        |

**Skype for Business および Microsoft Teams (既定)**

| XML 表記                | XML 値      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   True         |
| \<SfbMeetingEnabled>        |   True         |
| \<IsTeamsDefaultClient>     |   True        |

**Skype for Business のみ**

| XML 表記                | XML 値      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   False         |
| \<SfbMeetingEnabled>        |   True         |
| \<IsTeamsDefaultClient>     |   False        |

**Microsoft Teamsのみ**

| XML 表記                | XML 値      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   True         |
| \<SfbMeetingEnabled>        |   False         |
| \<IsTeamsDefaultClient>     |   True        |


## <a name="supported-meeting-modes-app-version-48-or-lower"></a>サポートされている会議モード アプリ バージョン 4.8 以降

**Skype for Business (既定) および Microsoft Teams**

| XML 表記                | XML 値      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   True         |
|  \<IsTeamsDefaultClient>     |   False        |

**Skype for Business および Microsoft Teams (既定)**

| XML 表記                | XML 値      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   True         |
|  \<IsTeamsDefaultClient>     |   True         |

**Skype for Business のみ**

| XML 表記                | XML 値      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   False         |
|  \<IsTeamsDefaultClient>     |   False         |

## <a name="custom-theme-images"></a>ユーザー設定のテーマ画像

<a name="Themes"> </a>

ユーザー設定のテーマ画像ファイルは、`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`フォルダーに配置する必要があります。 \<CustomThemeImageUrl\>変数にファイル名と拡張子を入力します。
  
画像ファイルはちょうど 3840 x 1080 ピクセルであり、jpg、jpeg、png、bmp のいずれかの形式である必要があります。 組織でユーザー設定の画像が必要な場合、グラフィック デザイナーは[ユーザー設定のテーマ Photoshop テンプレート](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)を使用できます。 このテンプレートには、テーマ画像の残りの部分に関連したユーザー インターフェースの要素や、コンソールやディスプレイに表示される領域に関する詳細が記載されています。
  
テーマ画像を認識するには、デバイスの起動時に XML 構成ファイルを更新する必要があります。 新しい XML ファイルが処理され、削除されると、テーマのグラフィック ファイルはディレクトリから削除されます。

## <a name="locate-the-content-camera-usb-instance-path"></a>コンテンツ カメラの USB インスタンス パスを検索する

インスタント パスを検索する方法を次に示します。

1. Microsoft Teams Rooms コンソールの Windows 設定に移動します。
2. 管理者パスワードを入力します。
3. コマンドプロンプトで`devmgmt.msc`を入力して、デバイス マネージャーを開きます。
4. **デバイス マネージャー** で **イメージング デバイス** ノードを探し、コンテンツ カメラを見つけます。
5. カメラを右クリックし、[**プロパティ**] を開きます。
6. [**詳細**] タブを選び、ドロップダウンリストから [**デバイス インスタンスパス**] プロパティを見つけます。
7. 表示される値は、XML 構成ファイルに設定するデバイス インスタンス パスです。 XML でパスを指定する場合は、アンパサンド (&) を`&amp;`に置き換えます。

## <a name="set-front-row-as-the-default-layout"></a>フロント行を既定のレイアウトとして設定する

XML 構成でルームの既定の表示レイアウトを設定しない場合、既定のレイアウトはギャラリーに設定されます。 Front row を既定のレイアウトとして表示するには、XML 構成ファイルに追加 ```<DefaultFoRExperience>1</DefaultFoRExperience>``` します。

エンド ユーザーは、会議中にレイアウト ピッカーを使用して既定の表示レイアウトから切り替えることができます。

## <a name="turn-off-front-row"></a>フロント行をオフにする

フロント行は既定で有効になっています。 エンド ユーザーが特定の部屋でフロント行を使用することを許可しない場合は、フロント行をオフにします。 これを行うには、XML 構成ファイルに追加 ```<FrontRowEnabled>false</FrontRowEnabled>``` します。

## <a name="set-front-of-room-scale-and-resolution"></a>ルームのスケールと解像度の前面を設定する

Front of Room ディスプレイのスケールと解像度を設定するには、コンテナーを使用して XML 構成ファイルに`<MainFoRDisplay>`追加```<EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting>```します。 デバイスでデュアル ディスプレイを使用している場合は、コンテナーも含めます `<ExtendedFoRDisplay>` 。 

1 つの表示を使用してTeams ルームで両方と`<ExtendedFoRDisplay>`コンテナーを一緒に使用`<MainFoRDisplay>`する`<ExtendedFoRDisplay>`場合、コンテナーは無視されます。 詳細については、上記の XML と要素の例の表を参照してください。

## <a name="see-also"></a>関連項目

[コンテンツ カメラ](content-camera.md)

[Microsoft Teams Rooms の管理](rooms-manage.md)

[ファイル アイテムを構成する](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))
