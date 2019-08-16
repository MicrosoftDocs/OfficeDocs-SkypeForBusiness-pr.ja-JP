---
title: XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: この記事では、Microsoft Teams のルームデバイスで使用される既定の設定をリモート管理する方法について説明します。カスタムテーマの適用を含みます。
ms.openlocfilehash: c66aaba35fc678400118e67d7c66f362842c869f
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427623"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する

この記事では、Microsoft Teams のルームデバイスで使用される既定の設定をリモート管理する方法について説明します。カスタムテーマの適用を含みます。
  
マスター XML ファイルを更新して、ユーザーが管理するコンソールにコピーを送信すると、リモート管理されたデバイスの既定の設定を変更することができます。 この記事では、このようなファイルの作成方法を説明するとともに、リモート管理されたデバイス上にそれらを配置する方法を説明するリンクを示します。 このメソッドを使うと、Microsoft Teams のルームコンソールでカスタムテーマを実装することもできます。
  
## <a name="create-an-xml-configuration-file"></a>XML 構成ファイルを作成する

次の表では、このサンプル SkypeSettings (file name required) 構成ファイルに示されている要素について説明します。
  
```
<SkypeSettings>
    <AutoScreenShare>true</AutoScreenShare>
    <HideMeetingName>true</HideMeetingName>
    <UserAccount>
        <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
        <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
        <DomainUsername>Seattle\RanierConf</DomainUsername>
        <Password>password</Password>
        <ConfigureDomain>domain1, domain2</ConfigureDomain>
    </UserAccount>
    <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
    </Devices>
    <Theming>
        <ThemeName>Custom</ThemeName>
        <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
        <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
        </CustomThemeColor>
    </Theming>
</SkypeSettings>
```

XML ファイルの形式が正しくない (変数値が間違った型である、要素が不適切である、要素が閉じられているなど) 場合、エラーが検出された時点までの設定が検出された後、ファイルの残りの部分は無視されます。 XML 内の不明な要素は無視されます。 パラメーターは削除されると、変更されないままデバイス上に残ります。 パラメーターの値が無効な場合、その前の値は変更されません。
  
**XML 要素**

|要素|型|レベル|使用方法|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |すべての要素のコンテナー。 ||必須。 |
| \<AutoScreenShare\>  |ブール型 &#x2777;  |第1の &#x2776;  | true の場合、自動画面共有が有効になります。  |
|\<Hide会議名\> |ブール型 &#x2777;  |第1の &#x2776;  |true の場合、会議名が非表示になります。 |
|\<UserAccount\> |Container |第1の &#x2776;  |資格情報パラメーターのコンテナー。 通常、@contoso RanierConf<span></span>と同じように、サインインアドレス、Exchange アドレス、またはメールアドレスが同じになります。 |
|\<SkypeMeetingsEnabled\>  |ブール型 &#x2777;  |第1の &#x2776;  |既定では有効です。 |
|\<SkypeSignInAddress\> |文字列 &#x2778;  ||本体の SfB または Teams のデバイスアカウントのサインイン名です。 |
|\<ExchangeAddress\> |文字列 &#x2778;  ||コンソールの Exchange デバイス アカウントのサインイン名。 ExchangeAddress が省略された場合、SkypeSignInAddress は自動的には再利用されません。 |
|\<DomainUsername\> |文字列 &#x2778;  ||コンソール デバイスのドメイン名およびユーザー名 (Seattle\RanierConf など)。 |
|\<パスワード\> |String 3  || パスワード パラメーターは、Skype for Business デバイス アカウントのサインインで使用されるものと同一のパスワードです。  |
| \<ConfigureDomain\>  |文字列 &#x2778;  ||複数のドメインをコンマで区切ってリスト表示することができます。 |
|\<TeamsMeetingsEnabled\> |ブール型 &#x2777;  |第1の &#x2776;  |既定では無効です。 <br/> <br/> SkypeMeetingsEnabled \<\>と\<TeamsMeetingsEnabled\>の両方が無効になっている場合、XML ファイルの形式が不適切であると見なされますが、両方の設定を同時に有効にすることはできます。 |
|\<IsTeamsDefaultClient の> |ブール型 &#x2777;  |第1の &#x2776;  |既定では無効です。 |
|\<BluetoothAdvertisementEnabled> |ブール型 &#x2777;  |第1の &#x2776;  |既定では有効です。 |
|\<DualScreenMode\>  |ブール型 &#x2777;  |第1の &#x2776;  |True の場合、デュアルスクリーンモードが有効になります。 それ以外の場合は、デバイスでシングルスクリーンモードが使用されます。 |
|\<SendLogs\> |Container |第1の &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\> |文字列 &#x2778;  || "フィードバックを送信する" ウィンドウが表示されたときに、ログに記録できるメールアドレス (省略可能) を設定します。 |
|\<SendLogsAndFeedback\> |ブール型 &#x2777;  || true の場合、ログが管理者に送信されます。それ以外の場合、フィードバックのみが管理者に送信されます (ログは送信されません)。  |
| \<Devices\>  |Container |第1の &#x2776;  | 子要素内の接続済みのオーディオ デバイス名は、デバイス マネージャー アプリにリスト表示された値と同一のものになります。 この構成には、現在コンソールに接続していない A/V デバイスなど、現在システムに存在しないデバイスを含めることができます。 この構成はそれぞれのデバイスに対して保持されます。  |
|\<マイクロフォン Forcommunication\> |文字列 &#x2778;  ||会議でレコーディングデバイスとして使用するマイクを設定します。 |
|\<SpeakerForCommunication\> |文字列 &#x2778;  ||会議のスピーカーとして使用されるデバイス。 この設定は、使用されるスピーカー デバイスに、通話中の音声を聞かせるよう設定するために使用されます。 |
|\<DefaultSpeaker\> |文字列 &#x2778;  ||HDMI インジェスト ソースから音声を再生するために使用されるデバイス。 |
|\<ContentCameraId>  | 文字列 &#x2778;  | | 会議でアナログホワイトボードコンテンツを共有するために、room で構成されているカメラのインスタンスパスを定義します。 「[コンテンツカメラの USB インスタンスパスを見つける」を](#locate-the-content-camera-usb-instance-path)参照してください。|
|\<ContentCameraInverted>  | ブール型 &#x2777; | | コンテンツカメラが物理的に上下逆さまにインストールされているかどうかを指定します。 自動回転をサポートするコンテンツカメラの場合は、false を指定します。 |
|\<ContentCameraEnhancement>  | ブール型 &#x2777; | |True (既定値) に設定すると、コンテンツカメラの画像がデジタルで強化されます。ホワイトボードの端が検出され、適切なズームが選択され、ホワイトボードに書いた人が透明になります。  <br><br> この値を false に設定すると、ホワイトボードがペンで描画されていないスペースの会議参加者に生のビデオフィードを送信することになります。代わりに、付箋やポスターなどのメディアを表示するためにカメラが使用されます。  |
| \<テーマ\>  |Container |第1の &#x2776;  |XML ファイルを使用して適用できる機能の 1 つに、所属組織のカスタム テーマがあります。 テーマ名、背景画像、色を指定できます。 |
|\<グループ名\> |文字列 &#x2778;  || クライアントのテーマを特定するために使用されます。 テーマ名のオプションは、既定、提供されたプリセット テーマのいずれか、またはカスタムになります。 <br/>  カスタム テーマ名は常に *Custom* という名前を使います。クライアント UI は、コンソールで、既定またはプリセットのいずれかに設定できますが、カスタム テーマの適用は管理者によってリモートで設定する必要があります。<br/>  プリセット テーマには次のものが含まれます:  <br/>  Default <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  現在のテーマを無効にするには、[テーマなし] を使用します。  |
|\<CustomThemeImageUrl\> |文字列 &#x2778;  ||カスタムテーマを使用する場合は必須です。それ以外の場合は省略可能です。 ユーザー設定のテーマの画像の詳細については、以下の「[カスタムテーマの画像](xml-config-file.md#Themes)」セクションを参照してください。  |
|\<CustomThemeColor\> |Container ||\<\>Redcomponent \<、\>GreenComponent、および\<BlueComponent\>値のコンテナー。 これらの値はカスタム テーマを使用する場合に必要です。 |
|\<赤成分\> |Byte (0-255) ||赤のカラー コンポーネントを表します。 |
|\<GreenComponent\> |Byte (0-255) ||緑のカラー コンポーネントを表します。 |
|\<BlueComponent\> |Byte (0-255) ||青のカラー コンポーネントを表します。 |
| | | |
 
第1レベルのすべての要素を省略可能 &#x2776; します。 第1レベルの要素を省略した場合、そのすべての子パラメーターはデバイス上でそのまま保持されます。
  
&#x2777; ブール型のフラグには、true、false、0、1のいずれかを指定できます。 ブール値または数値を空のままにすると、XML の形式が無効になり、設定が変更されるのを防ぐことができます。
  
 &#x2778; 文字列パラメーターが存在する場合は empty、empty が有効な値の場合は、デバイスでパラメーターが消去されます。
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>XML 構成ファイルを使用したコンソール設定の管理

起動時に、Microsoft Teams の [会議室] コンソールで、 **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**に SkypeSettings .xml という名前の xml ファイルが検出されると、構成設定が適用されます。XML ファイルで指定された XML ファイルを削除します。
  
エンタープライズに搭載されている Microsoft Teams の会議室の数や、それらを構成するための管理方法に応じて、XML 構成ファイルを配置する方法はいくつかあります。 ファイルがコンソールにプッシュされたら、再起動して構成の変更を処理します。 処理に成功すると、XML 構成ファイルが削除されます。 Microsoft Teams 室のデバイスに提案された管理方法については、次のトピックをご覧ください。
  
- [Microsoft Teams ルームのグループポリシーを構成する](room-systems-v2-operations.md#GroupPolicy)

- [PowerShell を使用したリモート管理](room-systems-v2-operations.md#RemotePS)と[ファイル項目の構成](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

ファイルの転送と、コンソール デバイス上での再起動のトリガーができるのであれば、いずれの方法も使用できます。 ファイルは、デバイスのローカルユーザーアカウントによって読み取り可能、書き込み可能、削除可能である必要があります (推奨されるのは、そのユーザーに対して権限が与えられている必要があります)。 ファイルの権限が適切に設定されていない場合、ソフトウェアは設定の適用に失敗したり、処理成功時にファイルの削除に失敗する可能性があるだけではなく、クラッシュする可能性があります。
  
## <a name="custom-theme-images"></a>カスタム テーマの画像

<a name="Themes"> </a>

**C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**にユーザー設定のテーマの画像ファイルを配置する必要があります。 \<CustomThemeImageUrl\>変数にファイル名と拡張子を入力します。
  
画像ファイルは、正確に3840X1080 ピクセルであり、jpg、jpeg、png、bmp のいずれかのファイル形式である必要があります。 組織でカスタム画像が必要な場合は、グラフィックデザイナーで[カスタムテーマ Photoshop テンプレート](https://go.microsoft.com/fwlink/?linkid=870441)を使うことができます。 このテンプレートには、テーマ画像内でいろいろな要素を配置できる場所や、コンソールやディスプレイに表示される領域に関する詳細が記載されています。
  
XML 構成ファイルはデバイスの起動時に更新され、テーマ画像を認識する必要があります。 新しい XML ファイルが処理されて削除されると、テーマのグラフィックファイルがディレクトリから削除されます。
  
## <a name="locate-the-content-camera-usb-instance-path"></a>コンテンツカメラの USB インスタンスパスを見つける

インスタンスパスを検索するには:

1. Microsoft Teams ルームコンソールの [Windows の設定] に移動します。
2. 管理者パスワードを入力します。
3. コマンドプロンプトで、「デバイス`devmgmt.msc`マネージャーの起動」と入力します。
4. **デバイスマネージャー**で、[**イメージングデバイス**] ノードを確認し、コンテンツカメラを探します。
5. カメラを右クリックして、[**プロパティ**] を開きます。
6. [**詳細**] タブを選択し、ドロップダウンで [**デバイスインスタンスパス**] プロパティを探します。
7. 表示される値は、XML 構成ファイルで設定するデバイスインスタンスパスです。 XML でパスを指定するときは、アンパサンド (&) を`&amp;`に置き換えます。

## <a name="see-also"></a>関連項目

[コンテンツのカメラ](content-camera.md)

[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)

[ファイルアイテムを構成する](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
