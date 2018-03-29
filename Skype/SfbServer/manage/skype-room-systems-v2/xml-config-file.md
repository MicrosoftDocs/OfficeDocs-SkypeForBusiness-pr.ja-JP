---
title: Skype Room Systems バージョン 2 のコンソールの設定を、XML 構成ファイルを使用してリモートで管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: この資料では、カスタム テーマの適用を含め、Skype ルーム システム v2 デバイスによって使用される既定の設定のリモート管理について説明します。
ms.openlocfilehash: 14891401c8cd13f35879ea064f2be49f88b1c68a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-a-skype-room-systems-v2-console-settings-remotely-with-an-xml-configuration-file"></a>Skype Room Systems バージョン 2 のコンソールの設定を、XML 構成ファイルを使用してリモートで管理する
 
この資料では、カスタム テーマの適用を含め、Skype ルーム システム v2 デバイスによって使用される既定の設定のリモート管理について説明します。
  
マスター XML ファイルを更新して、ユーザーが管理するコンソールにコピーを送信すると、リモート管理されたデバイスの既定の設定を変更することができます。 この記事では、このようなファイルの作成方法を説明するとともに、リモート管理されたデバイス上にそれらを配置する方法を説明するリンクを示します。 このメソッドを使用すると、Skype ルーム システム v2 のコンソールのカスタム テーマを実装することもできます。 
  
## <a name="creating-an-xml-configuration-file"></a>XML 構成ファイルの作成

このサンプル (これは、必要なファイル名) を SkypeSettings.xml に示すように要素を説明する次の表の構成ファイルです。 
  
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
             <AutoRotatePassword>1</AutoRotatePassword>
  </UserAccount>    
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

XML ファイルの作成でエラーが含まれる場合 (変数値の型に誤りがある、要素の配置順序に誤りがある、要素が閉じられていないなどの場合)、エラーが見つかった場所までの設定が適用され、処理中はファイルの残りの部分は無視されます。 XML 内の不明な要素は無視されます。 パラメーターは削除されると、変更されないままデバイス上に残ります。 パラメーターの値が有効である場合は、前の値は変更されません。
  
**XML 要素**
 
|**要素**|**タイプ**|**レベル**|**使用法**|
|:-----|:-----|:-----|:-----|
|\<SkypeSettings\>  <br/> |すべての要素のコンテナー。  <br/> ||必須。  <br/> |
| \<AutoScreenShare\> <br/> |ブール値 & #x 2777 です。 <br/> |最初 & #x 2776。 <br/> | true の場合、自動画面共有が有効になります。 <br/> |
|\<HideMeetingName\>  <br/> |ブール値 & #x 2777 です。 <br/> |最初 & #x 2776。 <br/> |true の場合、会議名が非表示になります。  <br/> |
|\<ユーザー アカウント\>  <br/> |Container  <br/> |最初 & #x 2776。 <br/> |資格情報パラメーターのコンテナー。  <br/> サインイン アドレス、Exchange アドレス、または電子メール アドレスは、通常は同一のものとなります (RanierConf@contoso.com など)。  <br/> |
|\<SkypeMeetingsEnabled\>  <br/> |ブール値 & #x 2777 です。 <br/> |最初 & #x 2776。 <br/> |既定では有効です。  <br/> |
|\<TeamsMeetingsEnabled\>  <br/> |ブール値 & #x 2777 です。 <br/> |最初 & #x 2776。 <br/> |既定では無効です。  <br/> XML ファイルと見なされます正しくない場合は両方\<SkypeMeetingsEnabled\>と\<TeamsMeetingsEnabled\>が無効になって、両方の設定が同時に有効にすることができますが、します。  <br/> |
|\<SkypeSignInAddress\>  <br/> |文字列 3 <br/> ||コンソールの Skype for Business デバイス アカウントのサインイン名。  <br/> |
|\<ExchangeAddress\>  <br/> |文字列 3 <br/> ||コンソールの Exchange デバイス アカウントのサインイン名。  <br/> ExchangeAddress が省略された場合、SkypeSignInAddress が自動的に再利用されることはありません。  <br/> |
|\<DomainUsername\>  <br/> |文字列 & #x 2778 です。 <br/> ||コンソール デバイスのドメイン名およびユーザー名 (Seattle\RanierConf など)。  <br/> |
|\<パスワード\>  <br/> |文字列 3 <br/> || パスワード パラメーターは、Skype for Business デバイス アカウントのサインインで使用されるものと同一のパスワードです。 <br/> |
| \<ConfigureDomain\> <br/> |文字列 & #x 2778 です。 <br/> ||複数のドメインをコンマで区切ってリスト表示することができます。  <br/> |
|\<AutoRotatePassword\>  <br/> |ブール値 & #x 2777 です。 <br/> |||
| \<DualScreenMode\> <br/> |ブール値 & #x 2777 です。 <br/> |最初 & #x 2776。 <br/> |True の場合、デュアル画面モードを有効にします。 それ以外の場合、デバイスでは 1 画面表示モードが使用されます。  <br/> |
|\<SendLogs\>  <br/> |Container  <br/> |最初 & #x 2776。 <br/> ||
|\<EmailAddressForLogsAndFeedback\>  <br/> |文字列 & #x 2778 です。 <br/> ||[フィードバックの送信] ウィンドウが表示されたときにログの送信先となるオプションの電子メール アドレスを設定します。  <br/> |
|\<SendLogsAndFeedback\>  <br/> |ブール値 & #x 2777 です。 <br/> || true の場合、ログが管理者に送信されます。それ以外の場合、フィードバックのみが管理者に送信されます (ログは送信されません)。 <br/> |
| \<デバイス\> <br/> |Container  <br/> |最初 & #x 2776。 <br/> | 子要素内の接続済みのオーディオ デバイス名は、デバイス マネージャー アプリにリスト表示された値と同一のものになります。 この構成には、現在コンソールに接続していない A/V デバイスなど、現在システムに存在しないデバイスを含めることができます。 この構成はそれぞれのデバイスに対して保持されます。 <br/> |
|\<MicrophoneForCommunication\>  <br/> |文字列 3 <br/> ||会議で録音デバイスとして使用されるマイクを設定します。  <br/> |
|\<SpeakerForCommunication\>  <br/> |文字列 3 <br/> ||会議のスピーカーとして使用されるデバイス。 この設定は、使用されるスピーカー デバイスに、通話中の音声を聞かせるよう設定するために使用されます。  <br/> |
|\<DefaultSpeaker\>  <br/> |文字列 3 <br/> ||HDMI インジェスト ソースから音声を再生するために使用されるデバイス。  <br/> |
| \<テーマ\> <br/> |Container  <br/> |最初 & #x 2776。 <br/> |XML ファイルを使用して適用できる機能の 1 つに、所属組織のカスタム テーマがあります。 テーマの名前、背景イメージ、および色を指定することができます。  <br/> |
|\<ThemeName\>  <br/> |文字列 & #x 2778 です。 <br/> || クライアントのテーマを特定するために使用されます。 テーマ名のオプションは、既定、提供されたプリセット テーマのいずれか、またはカスタムになります。 <br/>  カスタム テーマの名前は、*カスタム*の名前を常に使用する必要があります。 クライアント UI は、コンソールで、既定またはプリセットのいずれかに設定できますが、カスタム テーマの適用は管理者によってリモートで設定する必要があります。 <br/>  プリセット テーマには次のものが含まれます:  <br/>  Default <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  現在のテーマを無効にするのには、ThemeName の [テーマなし] を使用します。 <br/> |
|\<CustomThemeImageUrl\>  <br/> |文字列 & #x 2778 です。 <br/> ||それ以外の場合に省略可能なユーザー定義のテーマを使用する場合に必要です。 カスタム テーマの画像の詳細については[カスタム テーマの画像](xml-config-file.md#Themes)の項を参照してください。 <br/> |
|\<CustomThemeColor\>  <br/> |Container  <br/> ||コンテナー、 \<RedComponent\>、 \<GreenComponent\>、および\<BlueComponent\>の値です。 これらの値はカスタム テーマを使用する場合に必要です。  <br/> |
|\<RedComponent\>  <br/> |Byte (0-255)  <br/> ||赤のカラー コンポーネントを表します。  <br/> |
|\<GreenComponent\>  <br/> |Byte (0-255)  <br/> ||緑のカラー コンポーネントを表します。  <br/> |
|\<BlueComponent\>  <br/> |Byte (0-255)  <br/> ||青のカラー コンポーネントを表します。  <br/> |
   
& #x 2776。第 1 レベルの要素はすべてオプションです。 第 1 レベルの要素を省略すると、デバイス上のすべての子のパラメーターは変更されません。
  
& #x 2777 です。ブール型のフラグは、次のいずれかを指定できます。 true、false、0、または 1 です。 ブール値または数値の値を空のままに可能性があります XML を表示形式が正しくない設定を変更するがないようにします。
  
 & #x 2778 です。文字列パラメーターは、表示、空の場合、および有効な値は、空には、デバイスのパラメーターがクリアされます。
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>XML 構成ファイルを使用したコンソール設定の管理

Skype ルーム システム v2 のコンソールの場所に SkypeSettings.xml という名前の XML ファイルを検索する場合は、起動時に * * C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState** に示されている構成設定が適用されますXML ファイルで XML ファイルを削除します。
  
Skype ルーム システム v2 デバイスの数によって、企業があり、それらを構成するのには管理するために選択する方法がいくつかの XML 構成ファイルを配置する方法。 ファイルがコンソールにプッシュされたら、再起動して構成の変更を処理します。 処理に成功すると、XML 構成ファイルが削除されます。 Skype ルーム システム v2 のデバイスの管理の方法で説明します。
  
- [Skype Room Systems v2 のグループ ポリシーの構成](skype-room-systems-v2.md#GroupPolicy)
    
- [PowerShell を使用してリモートの管理](skype-room-systems-v2.md#RemotePS)」および「[ファイル項目を構成します。](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)
    
ファイルの転送と、コンソール デバイス上での再起動のトリガーができるのであれば、いずれの方法も使用できます。 ファイルは、読み取り、書き込み可能なおよび削除可能なデバイスのローカル ユーザー アカウント (可能であれば、それが所有する必要があり、そのユーザーに与えられる全体の特権を持っている) でなければなりません。 ファイルの権限が適切に設定されていない場合、ソフトウェアは設定の適用に失敗したり、処理成功時にファイルの削除に失敗する可能性があるだけではなく、クラッシュする可能性があります。
  
## <a name="custom-theme-images"></a>カスタム テーマの画像
<a name="Themes"> </a>

カスタム テーマの画像ファイルを配置する必要があります**C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**で入力ファイル名と拡張子で、<CustomThemeImageUrl>変数です。
  
画像ファイルは正確に 3840X1080 ピクセルで、ファイル形式は jpg、jpeg、png、bmp のいずれかである必要があります。 組織では、カスタム イメージを希望する場合は、グラフィック デザイナーに役立つ、[カスタム テーマの Photoshop のテンプレート](https://go.microsoft.com/fwlink/?linkid=870441)。 テーマ画像にさまざまな要素を配置する場所や、本体とディスプレイに表示される領域をさらに詳細が含まれています。
  
XML 構成ファイルはデバイスの起動時に更新され、テーマ画像を認識する必要があります。新しい XML ファイルが処理され、削除されると、テーマのグラフィック ファイルはディレクトリから削除されます。
  
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Themes"> </a>

#### 

[Skype ルームの管理システム v2](skype-room-systems-v2.md)
#### 

[ファイル項目を構成します。](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)

