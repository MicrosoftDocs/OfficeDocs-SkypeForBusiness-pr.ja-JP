---
title: XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: この記事では、Microsoft Teams のルームデバイスで使用される既定の設定をリモート管理する方法について説明します。カスタムテーマの適用を含みます。
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305334"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する
 
この記事では、Microsoft Teams のルームデバイスで使用される既定の設定をリモート管理する方法について説明します。カスタムテーマの適用を含みます。
  
マスター XML ファイルを更新して、ユーザーが管理するコンソールにコピーを送信すると、リモート管理されたデバイスの既定の設定を変更することができます。 この記事では、このようなファイルの作成方法を説明するとともに、リモート管理されたデバイス上にそれらを配置する方法を説明するリンクを示します。 このメソッドを使うと、Microsoft Teams のルームコンソールでカスタムテーマを実装することもできます。 
  
## <a name="creating-an-xml-configuration-file"></a>XML 構成ファイルの作成

次の表では、このサンプル SkypeSettings で示されている要素について説明しています (これは必須のファイル名) 構成ファイルです。 
  
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

XML ファイルの作成でエラーが含まれる場合 (変数値の型に誤りがある、要素の配置順序に誤りがある、要素が閉じられていないなどの場合)、エラーが見つかった場所までの設定が適用され、処理中はファイルの残りの部分は無視されます。 XML 内の不明な要素は無視されます。 パラメーターは削除されると、変更されないままデバイス上に残ります。 パラメーターの値が無効な場合、その前の値は変更されません。
  
**XML 要素**
 
|要素|型|レベル|使用方法|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |すべての要素のコンテナー。   ||必須。   |
| \<AutoScreenShare\>  |ブール値 & # x2777;  |第1の & # x2776;  | true の場合、自動画面共有が有効になります。  |
|\<Hide会議名\>   |ブール値 & # x2777;  |第1の & # x2776;  |true の場合、会議名が非表示になります。   |
|\<UserAccount\>   |Container   |第1の & # x2776;  |資格情報パラメーターのコンテナー。   通常、@contoso RanierConf と同じように、サインインアドレス、Exchange アドレス、またはメールアドレスが同じになります。   |
|\<SkypeMeetingsEnabled\>  |ブール値 & # x2777;  |第1の & # x2776;  |既定では有効です。   |
|\<SkypeSignInAddress\>   |文字列 & # x2778;  ||コンソールの Skype for Business デバイス アカウントのサインイン名。   |
|\<ExchangeAddress\>   |文字列 & # x2778;  ||コンソールの Exchange デバイス アカウントのサインイン名。   ExchangeAddress が省略された場合、SkypeSignInAddress が自動的に再利用されることはありません。   |
|\<DomainUsername\>   |文字列 & # x2778;  ||コンソール デバイスのドメイン名およびユーザー名 (Seattle\RanierConf など)。   |
|\<パスワード\>   |String 3  || パスワード パラメーターは、Skype for Business デバイス アカウントのサインインで使用されるものと同一のパスワードです。  |
| \<ConfigureDomain\>  |文字列 & # x2778;  ||複数のドメインをコンマで区切ってリスト表示することができます。   |
|\<TeamsMeetingsEnabled\>   |ブール値 & # x2777;  |第1の & # x2776;  |既定では無効です。 <br/> <br/> SkypeMeetingsEnabled \<\>と\<TeamsMeetingsEnabled\>の両方が無効になっている場合、XML ファイルの形式が不適切であると見なされますが、両方の設定を同時に有効にすることはできます。   |
|\<IsTeamsDefaultClient> |ブール値 & # x2777;  |第1の & # x2776;  |既定では無効です。 |
|\<BluetoothAdvertisementEnabled> |ブール値 & # x2777;  |第1の & # x2776;  |既定では有効です。 |
|\<DualScreenMode\>  |ブール値 & # x2777;  |第1の & # x2776;  |True の場合、デュアルスクリーンモードが有効になります。 それ以外の場合、デバイスでは 1 画面表示モードが使用されます。   |
|\<SendLogs\>   |Container   |第1の & # x2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |文字列 & # x2778;  ||[フィードバックの送信] ウィンドウが表示されたときにログの送信先となるオプションの電子メール アドレスを設定します。   |
|\<SendLogsAndFeedback\>   |ブール値 & # x2777;  || true の場合、ログが管理者に送信されます。それ以外の場合、フィードバックのみが管理者に送信されます (ログは送信されません)。  |
| \<Devices\>  |Container   |第1の & # x2776;  | 子要素内の接続済みのオーディオ デバイス名は、デバイス マネージャー アプリにリスト表示された値と同一のものになります。 この構成には、現在コンソールに接続していない A/V デバイスなど、現在システムに存在しないデバイスを含めることができます。 この構成はそれぞれのデバイスに対して保持されます。  |
|\<マイクロフォン Forcommunication\>   |文字列 & # x2778;  ||会議で録音デバイスとして使用されるマイクを設定します。   |
|\<SpeakerForCommunication\>   |文字列 & # x2778;  ||会議のスピーカーとして使用されるデバイス。 この設定は、使用されるスピーカー デバイスに、通話中の音声を聞かせるよう設定するために使用されます。   |
|\<DefaultSpeaker\>   |文字列 & # x2778;  ||HDMI インジェスト ソースから音声を再生するために使用されるデバイス。   |
| \<テーマ\>  |Container   |第1の & # x2776;  |XML ファイルを使用して適用できる機能の 1 つに、所属組織のカスタム テーマがあります。 テーマ名、背景画像、色を指定できます。   |
|\<グループ名\>   |文字列 & # x2778;  || クライアントのテーマを特定するために使用されます。 テーマ名のオプションは、既定、提供されたプリセット テーマのいずれか、またはカスタムになります。 <br/>  ユーザー設定のテーマ名には、常に*ユーザー設定*の名前を使用する必要があります。 クライアント UI は、コンソールで、既定またはプリセットのいずれかに設定できますが、カスタム テーマの適用は管理者によってリモートで設定する必要があります。 <br/>  プリセット テーマには次のものが含まれます:  <br/>  Default <br/>  Blue Wave <br/>  Digital Forest <br/>  Dreamcatcher <br/>  Limeade <br/>  Pixel Perfect <br/>  Roadmap <br/>  Sunset <br/>  現在のテーマを無効にするには、[テーマなし] を使用します。  |
|\<CustomThemeImageUrl\>   |文字列 & # x2778;  ||カスタムテーマを使用する場合は必須です。それ以外の場合は省略可能です。 ユーザー設定のテーマの画像の詳細については、以下の「[カスタムテーマの画像](xml-config-file.md#Themes)」セクションを参照してください。  |
|\<CustomThemeColor\>   |Container   ||\<\>Redcomponent \<、\>GreenComponent、および\<BlueComponent\>値のコンテナー。 これらの値はカスタム テーマを使用する場合に必要です。   |
|\<赤成分\>   |Byte (0-255)   ||赤のカラー コンポーネントを表します。   |
|\<GreenComponent\>   |Byte (0-255)   ||緑のカラー コンポーネントを表します。   |
|\<BlueComponent\>   |Byte (0-255)   ||青のカラー コンポーネントを表します。   |
| | | |
   
&#x2776;第1レベルのすべての要素は省略可能です。 第1レベルの要素を省略した場合、そのすべての子パラメーターはデバイス上でそのまま保持されます。
  
&#x2777;ブール型のフラグには、true、false、0、1のいずれかを指定できます。 ブール値または数値を空にすると、XML の形式が無効になり、設定が変更されなくなる可能性があります。
  
 &#x2778;文字列パラメーターが存在する場合は、empty と empty が有効な値である場合、デバイス上のパラメーターは消去されます。
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>XML 構成ファイルを使用したコンソール設定の管理

起動時に、Microsoft Teams の [会議室] コンソールで、 **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**に SkypeSettings .xml という名前の xml ファイルが検出されると、構成設定が適用されます。XML ファイルで指定された XML ファイルを削除します。
  
エンタープライズに搭載されている Microsoft Teams の会議室の数や、それらを構成するためにどのように管理するかに応じて、さまざまな方法で XML 構成ファイルを配置できます。 ファイルがコンソールにプッシュされたら、再起動して構成の変更を処理します。 処理に成功すると、XML 構成ファイルが削除されます。 Microsoft Teams 室のデバイスに提案された管理方法については、次のトピックをご覧ください。
  
- [Microsoft Teams ルームのグループポリシーを構成する](room-systems-v2-operations.md#GroupPolicy)
    
- [PowerShell を使用したリモート管理](room-systems-v2-operations.md#RemotePS)と[ファイル項目の構成](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
ファイルの転送と、コンソール デバイス上での再起動のトリガーができるのであれば、いずれの方法も使用できます。 ファイルは、デバイスのローカルユーザーアカウントによって読み取り可能、書き込み可能、削除可能である必要があります (推奨されるのは、そのユーザーに対して権限が与えられている必要があります)。 ファイルの権限が適切に設定されていない場合、ソフトウェアは設定の適用に失敗したり、処理成功時にファイルの削除に失敗する可能性があるだけではなく、クラッシュする可能性があります。
  
## <a name="custom-theme-images"></a>カスタム テーマの画像
<a name="Themes"> </a>

**C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**にユーザー設定のテーマの画像ファイルを配置する必要があります。 \<CustomThemeImageUrl\>変数にファイル名と拡張子を入力するだけです。
  
画像ファイルはちょうど 3840 x 1080 ピクセルであり、jpg、jpeg、png、bmp のいずれかの形式である必要があります。 組織でカスタム画像が必要な場合は、グラフィックデザイナーを使用すると、[ユーザー設定のテーマの Photoshop テンプレート](https://go.microsoft.com/fwlink/?linkid=870441)が役に立ちます。 このテンプレートには、テーマ画像内でいろいろな要素を配置できる場所や、コンソールやディスプレイに表示される領域に関する詳細が記載されています。
  
XML 構成ファイルはデバイスの起動時に更新され、テーマ画像を認識する必要があります。新しい XML ファイルが処理され、削除されると、テーマのグラフィック ファイルはディレクトリから削除されます。
  
## <a name="see-also"></a>関連項目


[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)

[ファイルアイテムを構成する](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
