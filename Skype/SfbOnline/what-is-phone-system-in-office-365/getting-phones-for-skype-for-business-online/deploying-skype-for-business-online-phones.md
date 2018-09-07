---
title: Skype for Business Online 電話機の展開レポート
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 適切なファームウェアを取得する、必要な場合に更新する、ライセンスを割り当てる、そして Skype for Business オンラインの電話の設定を構成する配置手順を学びます。
ms.openlocfilehash: 3b695f0198e5edb23a8746babb071742d7b7712f
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860461"
---
# <a name="deploying-skype-for-business-online-phones"></a>Skype for Business Online 電話機の展開レポート

[] このガイドは Skype for Business Online IP 電話機の展開をサポートするガイドです。
  
あらゆる種類のビジネスにおいて、音声通話を発受信するための電話番号を確保することは、ビジネスを運営する上で重要な条件です。電話番号を有するユーザーは、IP 電話機、PC、モバイル デバイスを含むすべての Skype for Business デバイスで音声通話を行うことができます。Skype for Business IP 電話機の詳細については、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」をご覧ください。
  
## <a name="deployment-steps-for-ip-phones"></a>IP 電話機の展開手順

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>ステップ 1 - メーカーの管理者ガイドと電話機のマニュアルのダウンロード

まず最初に、メーカーの管理ガイドと電話機のマニュアルをダウンロードすることをお勧めします。
  
- Polycom 電話の場合は、[Polycom 展開ガイド] を参照してください ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。
    
- Yealink 電話機については、『[Yealink Skype for Business HD SIP Phones Solution (Yealink Skype for Business HD SIP 電話機のソリューション)](http://www.yealink.com/products_top_2.html)』をご覧ください。
    
- AudioCodes 電話機については、『[Audiocodes Provisioning Management Guide (Audiocodes プロビジョニング管理ガイド)](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)』をご覧ください。
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>ステップ 2 - Skype for Business 対応 IP 電話機およびファームウェアを購入または移行していることを確認する

Skype for Business Online 対応の電話機およびファームウェアは、Skype for Business Server にも互換性がありますが、その逆の互換性は必ずしも保証されません。対応している電話機とファームウェアを購入またはプロビジョニングしていることを確認するには、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」の説明をご覧ください。
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>ステップ 3 - 正しいファームウェアがインストールされていることを確認し、必要に応じてファームウェアを更新する

お使いの電話機のファームウェア バージョンを、それぞれ以下の方法で確認します。
  
- **Polycom VVX 電話**の場合は、**[設定]** > **[ステータス]** > **[プラットフォーム]** > **[アプリケーション]** > **[メイン]** に移動します。
    
- **Yealink 電話機** の場合は、メインの電話画面で [ **Status (情報)** ] に移動します。
    
- **AudioCodes 電話**の場合は、**[メニュー]** > **[デバイス ステータス]** > **[ファームウェア バージョン]** に移動します。
    
    > [!NOTE]
    > 電話機の詳細設定へのリモート アクセスについては、メーカーの管理ガイドをご覧ください。ユーザー ガイドおよび電話機マニュアルについては、上記のリンクをご覧ください。 
  
- **Lync Phone Edition (LPE) 電話**: スタート画面から **[メニュー] ** > **[システム情報] **に移動します。
    
### <a name="step-4---device-update-considerations"></a>ステップ 4 - デバイス更新の考慮事項

> [!NOTE]
> 5.5.1.X より前の Polycom ファームウェアには、メーカー独自のデバイスのロック メカニズムが導入されています。このメカニズムは Skype for Business 実装の「電話のロック」に置換されています。「デバイスのロック」で保護されていた 5.4.X.X から「電話のロック」を備える 5.5.1.X に電話機をアップグレードすると、「デバイスのロック」から PIN コードが継承されないため、電話機が保護されていない状態になります。「デバイスのロック」を有効にしていたユーザーは、次の Polycom デバイスのプロファイル パラメーターを有効にして、ユーザーがアップグレードのタイミングを制御できるようにする必要があります (lync.deviceUpdate.popUpSK.enabled=1)。 
  
ファームウェアの更新は Skype for Business Service によって管理されます。Skype for Business 認定済みの電話機のファームウェアは Skype for Business Update サーバーにアップロードされます。既定では、デバイスの更新はすべての電話機で有効になっています。電話機の無通信時間およびポーリング間隔に応じて、電話機では最新の認定済みビルドがダウロードされ、インストールされます。デバイスの更新設定は [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) コマンドレットを使用して、 _EnableDeviceUpdate_ パラメーターを `false` に設定することで無効にできます。
  
![電話を配置しています。](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
新しいファームウェアが利用可能になり、ダウンロードとインストールの準備が整うと、電話機が通知を受信します。Polycom 電話機では、ユーザーは通知を受信し、[ **Update (更新)** ] または [ **Postpone (延期)** ] のいずれかを選択できます。
  
![電話を配置しています。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Polycom 電話機の場合は、 **SwUpdate** を選択することで電話機のファームウェアを更新できます。
  
![電話を配置しています。](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
パートナーのプロビジョニング システムを使用してファームウェアの更新を管理するように選択することもできます。高度な電話機カスタマイズなど、パートナー プロビジョニング システム管理を行う場合は、製造元の管理ガイドをご覧ください。
  
> [!CAUTION]
> 更新のループを回避するため、単一のデバイス更新機関 (インバンド デバイス更新またはサードパーティー プロビジョニング サーバー) を利用してください。 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>ステップ 5 - 電話の設定の構成とインフラ整備

Skype for Business インバンド管理の Windows PowerShell コマンドレットを使用して最も一般的に使用される電話機オプションをセットアップできます。これらのパラメーターおよび設定の詳細については、「[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)」をご覧ください。
  
ネットワーク インフラストラクチャの計画については、「[Skype Operations Framework (Skype の運用フレームワーク](https://www.skypeoperationsframework.com/)」をご覧ください。
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>ステップ 6 - ユーザーのサインインの準備

ユーザーが正常に Skype for Business Online 電話機にサインインし、通話できるようにするには、ユーザーに正しいライセンスが割り当てられていることを確認する必要があります。 最低でも、電話システムのライセンスと通話プランを割り当てる必要があります。 詳細については、 [Skype for Business と Microsoft Teams アドオン ライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) および [Skype for Business と Microsoft Teams ライセンスの割り当て](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を表示できます。
  
通話プランの詳細については、「[Office 365 の通話プランについて](/microsoftteams/what-are-calling-plans-in-office-365)」を読むことで確認できます。
  
- Online ユーザーが利用できる **サインイン オプション** は次のとおりです。
    
  - **Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。
    
     ![電話を配置しています。](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - **Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。
    
     ![Yealink 電話でログオンします。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    製造元ごとのサポートされるサインイン オプションの詳細については、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」をご覧ください。
    
- **ユーザー ID** ユーザーは、電話機のキーパッドまたは画面上のキーボード (利用可能な場合) を使用して、組織のユーザー名およびパスワードで電話機にサインインできます。たとえば、ユーザー名として *amosm@contoso.com*  のような UPN 形式を使用します。
    
     ![電話を配置しています。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > PIN 認証は、LPE およびパートナーの IP 電話機向けの Skype for Business Online ではサポートされていません。 
  
- **PC の使用** ユーザーの PC に Better Together over Ethernet (BToE) ソフトウェアがインストールされ、有効化されている場合、ユーザーは Windows Skype for Business アプリの認証ウィンドウを使用して電話機にログインできます。 その他の情報については、「[ステップ 7 (省略可能) - デバイス ペアリングおよび Better Together over Ethernet (BToE) を使用する場合](deploying-skype-for-business-online-phones.md#BK_BTOE)」をご覧ください。
    
    > [!NOTE]
    > ユーザーは、電話機にサインインするために組織のユーザー名およびパスワードを使用する必要があります。たとえば、ユーザー名として  *amosm@contoso.com*  のような UPN 形式を使用します。
  
     ![電話を配置しています。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Web サインインの使用**: これは、Online ユーザーが標準の Web ブラウザを使用して認証を行うことができる新しい方法です。ユーザーには、ブラウザを使ってサインインするときの手順が提供されます。
    
  - **Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。
    
     ![電話を配置しています。](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - **Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。
    
     ![Yealink 電話でログオンします。](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    生成されるコードの有効期限は 15 分です。期限が切れると、ユーザーは電話機に応じて [ **再試行**] または [ **OK**] をクリックして新しいコードを生成する必要があります。
    
  - **Polycom VVX 5XX/6XX** 電話機のユーザーには次の画面が表示されます。
    
     ![PIN コードの有効期限が切れています。](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - **Yealink T48G/T46G** 電話機のユーザーには次の画面が表示されます。
    
     ![Yealink 電話でログオンします。](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    ブラウザを使用して、電話機に表示されるアドレスに移動して、Skype for Business ユーザー名を入力します。
    
     ![電話を配置しています。](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    電話機に表示されるコードを入力します。
    
     ![電話を配置しています。](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    サイトに「[電話機メーカーの名前] **Skype for Business Certified Phone (Skype for Business 認定済みの電話機)**」と表示されていることを確認し、[ **続行**] をクリックします。
    
     ![電話を配置しています。](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    ユーザーの資格情報をクリックするか、[ **Use another account (別のアカウントを使用する)**] をクリックします。
    
     ![電話を配置しています。](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    下記のページが表示されたら、ブラウザを安全に閉じることができます。
    
     ![電話を配置しています。](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Skype for Business Online 向けの LPE 電話機は USB テザリングを介したサインインのみをサポートします。 
  
- **サポートされる展開** 次の表は、Exchange 統合、多要素認証 (MFA) による先進認証、Skype for Business Online およびオンプレミスといった現在サポートされている展開モデルの対応認証方法を示しています。
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**交換** <br/> |**電話機のサインイン方法** <br/> |**Skype For Business アクセス** <br/> |**先進認証と MFA を無効にした Exchange アクセス** <br/> |**先進認証と MFA を有効にした Exchange アクセス** <br/> |
|オンライン  <br/> |オンライン  <br/> |Web サイン イン  <br/> |あり  <br/> |あり  <br/> |あり  <br/> |
|オンライン  <br/> |オンライン  <br/> |ユーザー名/パスワード  <br/> |あり  <br/> |あり  <br/> |なし  <br/> |
|オンライン  <br/> |オンプレミス  <br/> |Web サイン イン  <br/> |あり  <br/> |なし  <br/> |なし  <br/> |
|オンライン  <br/> |オンプレミス  <br/> |ユーザー名/パスワード  <br/> |あり  <br/> |あり  <br/> |なし  <br/> |
|オンプレミス  <br/> |オンライン/オンプレミス  <br/> |PIN 認証  <br/> |あり  <br/> |なし  <br/> |なし  <br/> |
|オンプレミス  <br/> |オンライン/オンプレミス  <br/> |ユーザー名/パスワード  <br/> |あり  <br/> |あり  <br/> |該当なし  <br/> |
|オンプレミス  <br/> |オンライン/オンプレミス  <br/> |PC 経由のサイン イン(BTOE)  <br/> |あり  <br/> |あり  <br/> |該当なし  <br/> |
   
- **電話機の機能** 機能セットは IP 電話機パートナーによって多少異なる場合があります。 完全な機能セットについて、および各電話機メーカーの機能の詳細情報については、「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online.md)」をご覧ください。
    
- **電話のロック** は、電話機を保護するために Skype for Business 認定済み電話機に最近導入されてた機能です。この機能が有効な場合、ユーザーは正常な認証後に PIN を作成するように求められます。PIN の作成後、定義したアイドル タイムアウトを過ぎると電話機がロックされます。さらに、ユーザーは電話機を手動でロックするか、電話のペアリングを使用して電話のロックを同期させることもできます。電話のロックの PIN を複数回誤って入力すると、ユーザーが電話機からサインアウトされるか、管理者のコードを使用して電話機をロック解除する必要があります。ただし、これは電話機パートナーによって異なります。ユーザーの PIN は 6 桁から 15 桁です。
    
    既定で有効化されている組織の電話のロックの無効化、アイドル タイムアウトの変更、ロック時またはインバンド設定の未使用時にユーザーが通話できるかどうかの設定を行うことができます。これらの設定の詳細については、「[Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)」をご覧ください。
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>ステップ 7 (省略可能) - デバイス ペアリングおよび Better Together over Ethernet (BToE) を使用する場合
<a name="BK_BTOE"> </a>

BToE は、ユーザーの電話機を Windows Skype for Business アプリとペアリングさせるパートナー IP 電話機の電話ペアリング メカニズムです。BToE により、ユーザーを次の操作を行うことができます。
  
- Skype for Business デスクトップ アプリ (PC を使用) を使用して IP 電話機にサインインする
    
- 電話のロックを PC のロックと同期する
    
- クリックして通話する
    
BToE の動作は [ *自動*  ] (既定) および [ *手動*  ] の 2 つのモードで構成できます。Skype for Business のインバンド設定を使用して、ユーザーに対して有効 (既定) または無効にすることもできます。[ *手動*  ] モードでの動作では、電話機と Windows アプリをペアリングするために追加の手順が必要になります。
  
 **ユーザーに BToE を展開する方法**
  
1. PC ポートを使用して PC を電話機に接続します。
    
     ![電話を配置しています。](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. 次に示すリンクを使ってメーカーの Web サイトから最新の BToE ソフトウェアをダウンロードし、インストールします。ユーザーの利便性を向上するため、System Center Configuration Manager (SCCM) などの管理配布ソリューションを使用して BToE ソフトウェアを配布して、インストールすることができます。SCCM の使用については、「[System Center Configuration Manager のパッケージとプログラム](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs)」をご覧ください。
    
  - [Polycom BToE ソフトウェア ダウンロード サイト](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [Yealink BToE ソフトウェア ダウンロード](http://www.yealink.com/products_list_10.html)
    
  - [AudioCodes BToE ソフトウェア ダウンロード](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. 既定では、BToE のサーバー設定は [ **有効** ] および **自動モード** です。 これらの設定を変更するには、 [セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)を参照してください。
    
> [!NOTE]
> BToE は Mac および VDI プラットフォームでは現在サポートされていません。 
  
## <a name="related-topics"></a>関連トピック
[Skype for Business および Microsoft Teams のサービス電話番号の取得](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Office 365 での電話システムで利用できる機能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[国および地域ごとの電話会議および通話プランの利用可能性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
