---
title: 会議クライアントを計画する (Web アプリと会議アプリ)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: '概要: IT 担当者は、skype for business Server の計画時に Skype for Business Web App と Skype 会議アプリのサポート要件を確認する必要があります。 この記事は、これらのアプリのユーザーを対象としたものではありません。'
ms.openlocfilehash: 0e1ce225f99a112f11d55d76eb8039a10d9aac6b
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777792"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>会議クライアントを計画する (Web アプリと会議アプリ)
 
**概要:** IT 担当者は、skype for business Server の計画時に Skype for Business Web App と Skype 会議アプリのサポート要件を確認する必要があります。 この記事は、これらのアプリのユーザーを対象としたものではありません。
  
Skype for Business Server を実装したら、組織のユーザーには、展開プロセスの一環として Skype for Business クライアントがインストールされている可能性があります。 
  
後で、これらのユーザーは会議を作成し、組織外からユーザーを招待することができます。また、会議の出席者は、どのバージョンの Skype for Business クライアントも使用していない場合があります。 これらのユーザーが会議出席依頼の URL をクリックすると、クライアントが存在しないことが検出され、会議に参加できるように、会議専用クライアントをダウンロードしてインストールするように求められます。
  
> [!NOTE]
> Skype for Business Web App と Skype 会議アプリは、Skype for business を使用せずに会議にログインしようとした場合にのみ使用できます。 これらのアプリのユーザーヘルプは[https://aka.ms/smahelp](https://aka.ms/smahelp)、にあります。 
  
> [!NOTE]
> Skype for Business Web App または Skype 会議アプリを事前にインストールすることはできませんが、[スマートフォン](https://products.office.com/skype-for-business/download-app?tab=tabs-1)や[タブレット](https://products.office.com/skype-for-business/download-app?tab=tabs-2)ユーザーは、会議に参加するために使用できる安価なモバイルクライアントをインストールすることができます。
  
既定では、会議をホストしているサーバーは、会議に参加するために Skype for Business Web App をダウンロードしてインストールするようユーザーに指示します。 Skype for Business Web App はフロントエンドサーバーに格納され、会議の出席者に送信されます。 
  
Skype for business Server の場合、skype 会議アプリ (Windows 上) および skype for Business for Mac (on Mac) は、CU5 で始まる skype for Business Web App の代替として使用できますが、代替アプリを提供するには、「 [Enable Skype 会議アプリを使用して skype For Business Web app を置き換える (オプション)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)」で説明されている追加の  Skype 会議アプリと Skype for Business for Mac が有効になっている場合、ユーザーは Skype for Business サーバーからではなく、Office 365 コンテンツ配信ネットワーク (CDN) から最新バージョンのアプリをダウンロードします。 Skype for Business Server 2019 では、Skype 会議アプリと Skype for Business for Mac を使用することが唯一のオプションです。
  
Skype 会議アプリは、Internet Explorer のユーザーにワンクリック参加を含む、アプリをダウンロードしてインストールし、会議に参加するための簡単なブラウザーの操作性を提供します。 また、skype 会議アプリは、信頼性と会議の機能のために Skype for Business Web App に関して多くの改良が加えられています。 
  
> [!NOTE]
> Skype for business Server 2015 CU5 以降のバージョンでは、Skype for business Online を使用して開催された会議では、clientless ユーザーが Skype for business Web アプリに送信されなくなります。その代わりに、Skype 会議アプリ (Windows) または Skype for Business for Mac () が送信されます。 Skype for business Server 2015 CU5 以降のバージョンでは、skype for business [Web app を置き換えるように Skype 会議アプリを有効](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)にした場合 (オプション)、clientless ユーザーが Skype For Business web app ではなく、Skype 会議アプリまたは Skype for Business for Mac に送信されます。 
  
## <a name="software-requirements"></a>ソフトウェア要件
<a name="OS-Browser"> </a>

Skype for Business Web アプリを使用するには、次のサポートされているオペレーティングシステムとブラウザーの組み合わせのいずれかをユーザーが持つ必要があります。 
  
**Skype for Business Web App のオペレーティングシステムとブラウザーの最小サポート**

| オペレーティング システム | Edge | 32および64ビットの Internet Explorer 11 以降 | 32および64ビットの Internet Explorer 10 以降 | 32および64ビット版の Internet Explorer 9 以降 | 32および64ビットバージョンの Safari 6.2.8-11x | 32および64ビットバージョンの Chrome 18.x 以降 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |はい  <br/> |はい  <br/> |該当なし  <br/> |該当なし  <br/> |該当なし  <br/> |はい &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |該当なし  <br/> |はい  <br/> |該当なし  <br/> |該当なし  <br/> |該当なし <br/> |はい &#x2778; <br/> |
|Windows 8 (Intel ベース) &#x2776; <br/> |該当なし  <br/> |該当なし  <br/> |はい  <br/> |該当なし <br/> |該当なし  <br/> |はい &#x2778; <br/> |
|Windows 7 SP1 &#x2777; <br/> |該当なし  <br/> |はい  <br/> |いいえ  <br/> |いいえ  <br/> |N/A <br/>|はい &#x2778; <br/> |
|Windows Server 2008 R2 SP1 &#x2777; <br/> |該当なし  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |該当なし <br/>|はい &#x2778; <br/> |
|macOS 10.8 以降 (Intel ベース) &#x2777; <br/> |該当なし  <br/> |該当なし  <br/> |該当なし  <br/> |該当なし  <br/> |はい  <br/> |はい <br/> |
   
&#x2776; Skype for Business Web App browser プラグインには、コンピューターベースの音声、ビデオ、共有、および進行中の画面共有とその他の機能の表示を使用するための特定の共有プラグインが必要です。 会議の出席者は、会議に参加するとき、またはこれらの機能のいずれかを開始するときに、共有プラグインをインストールするオプションを指定します。 Windows 8 および Windows 8.1 では、Internet Explorer 10 または Internet Explorer 11 を実行しているデスクトップの場合にのみ、共有プラグインをインストールできます。 これらの機能は、デスクトップ以外のバージョンの Internet Explorer 10 および11では使用できません。 Firefox と Safari バージョン12.0 以降はサポートされなくなったことに注意してください。
  
&#x2777; サポートされている Windows 7、Windows Server 2008 R2、および Macintosh オペレーティングシステムでは、コンピューターベースの音声、ビデオ、アプリケーションの表示、アプリケーション共有、デスクトップ表示、デスクトップ共有などのすべての機能を使用できます。 これらの機能を使用するには、プロンプトが表示されたときにプラグインをインストールする必要があります。 Mac OS X バージョン10.7 は現在サポートされていないことに注意してください。  また、web アプリが OS X 10.15 以降にインストールされることはありません。  事前に移行する匿名参加シナリオをサポートする、最新バージョンの Skype for Business for Mac の使用をお勧めします。
  
Windows 上の Chrome から Web App にアクセスする &#x2778; は、埋め込みの Internet Explorer フレームに Web アプリを読み込む小さなプログラムを起動します。 このプログラムでは、サポートされているいずれかのバージョンの Internet Explorer をインストールして、Web アプリが正しく読み込まれるようにする必要があります。
  
> [!NOTE]
> Microsoft 365 および Office 365 のユーザーは、Skype for Business で Internet Explorer 10 以降を使用できます。 
  
### <a name="skype-meetings-app"></a>Skype 会議アプリ

Skype 会議アプリは、windows 10、windows 8.1、windows 8、Windows 7、および32と64ビットの Internet Explorer 11 以降がインストールされているコンピューター上でアプリとして実行されます。 
  
その他の依存関係については、「 [Skype 会議アプリでサポートされているプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)」を参照してください。
  
### <a name="skype-for-business-for-mac"></a>Skype for Business for Mac

Mac 版 Skype for Business は、macOS バージョン10.8 以降を使用しているコンピューター上で実行されます。 

## <a name="hardware-requirements"></a>ハードウェア要件
<a name="OS-Browser"> </a>

コンピューターのハードウェア要件は、オペレーティングシステムとブラウザーによって決定されます。 音声およびテレフォニー機能には、マイクとスピーカー、マイク付きヘッドセット、またはコンピューターと互換性のあるデバイスが必要です。 ビデオ機能には、コンピューターと互換性のあるビデオデバイスが必要です。 ビデオハードウェアサポートおよび想定されるビデオ品質の詳細については、「 [Skype For business クライアントのビデオの解像度](video-resolutions.md)」を参照してください。
  
## <a name="network-requirements"></a>ネットワーク要件
<a name="Network"> </a>

Skype for Business Web App または Skype 会議アプリのユーザーが会議接続の問題を経験している場合、「 [office 365 の url と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)」で説明されているように、office 365 をサポートするように組織のネットワークインフラストラクチャが構成されていない可能性があります。 これは、会議が Skype for Business Online または Skype for business Server のユーザーによって作成されたものである場合です。 
  
ユーザーが説明どおりに構成されていないネットワーク上にいる場合は、多くのアプリ機能が機能しないことや、会議に接続できない場合があります。
  
## <a name="supported-meetings-features"></a>サポートされている会議機能
<a name="BKMK_Conferencing"> </a>

次の表では、Skype for Business クライアント、Skype for Business Web App、Skype 会議アプリ、Lync Web App のユーザーが利用できる会議機能を比較します。 機能の比較のために lync Web App が表示されています。ユーザーは、会議が Lync 2013 サーバーでホストされている場合にのみ Lync Web App をダウンロードして使用します。

| 機能 | Skype for Business 2016 または2019クライアント | Mac クライアント上の Skype for Business | Skype 会議アプリ | Skype for Business の Web アプリ | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|ビデオの追加  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|認証された参加者のために音声を電話に切り替える  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ゲスト参加者用に音声を電話に切り替える  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|マルチパーティビデオの表示 (ギャラリービュー)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオベースの画面共有  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (表示専用)  <br/> |||
|会議内発表者コントロールの使用  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|詳細な会議名簿へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM メッセージを高い重要度として設定する  <br/> |&#x2714;|||||
|デスクトップの共有 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|プログラムの共有 (有効な場合)  <br/> |&#x2714;||&#x2714; (Windows 上のみ、プラグインが必要)  <br/> |&#x2714; (Windows 上のみ、プラグインが必要)  <br/> |&#x2714; (Windows 上のみ、プラグインが必要)  <br/> |
|別のユーザーの共有デスクトップまたはプログラムの制御を取得する  <br/> |&#x2714;||&#x2714; (Windows でのみ &#x2776;、プラグインが必要)  <br/> |&#x2714; (Windows でのみ &#x2776;、プラグインが必要)  <br/> |&#x2714; (Windows でのみ &#x2776;、プラグインが必要)  <br/> |
|別のユーザーが共有デスクトップまたはプログラムを制御できるようにする  <br/> |&#x2714;|||||
|匿名参加者の追加 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|名前によって参加者を招待する  <br/> |&#x2714;|&#x2714;||||
|電話番号で参加者を招待する  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参加者をメールで招待する  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|ダイヤルイン音声会議の使用  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|即時会議を開始する  <br/> |&#x2714;|&#x2714;||||
|会議を記録する  <br/> |&#x2714;|||||
|添付ファイルを追加してダウンロードする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイルの追加と提示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイルへの移動  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote の会議ノートを追加および編集する  <br/> |&#x2714;||編集のみ (追加不可)  <br/> |編集のみ (追加不可)  <br/> |編集のみ (追加不可)  <br/> |
|ホワイトボードの使用  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|投票の実行  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|他のユーザーと共有するファイルをアップロードする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|会議または電話会議の予約  <br/> |Outlook または Skype for Business Web Scheduler  <br/> |Outlook または Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |
|Q&amp;マネージャー  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|出席者のビデオを無効にする  <br/> |&#x2714;|||||
|会議 IM を無効にする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|対象ユーザーをミュートにする  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|全員を出席者にする  <br/> |&#x2714;|||||
|Skype 会議ブロードキャストの作成  <br/> |&#x2714;|||||
   
 &#x2776; 参加者は、Skype for Business、Lync for Mac 2011 または Communicator for Mac 2011 ユーザーによって共有されているデスクトップを制御できません。 これは、Max OSX の Skype for Business Web App でも動作しません。
  
 &#x2777; Skype for Business Online の場合、この機能を使用するには、Microsoft PSTN 会議、Exchange ユニファイドメッセージング、またはサードパーティの電話会議プロバイダーが必要です。
  
 Lync for Mac 2011 クライアントは、会議で Skype for Business Web App によって共有されている場合、Microsoft Office 2013 PowerPoint プレゼンテーションを表示できません &#x2778;。
  
## <a name="known-issues-and-troubleshooting"></a>既知の問題とトラブルシューティング
<a name="BKMK_Conferencing"> </a>

エンドユーザーの場合、これらのアプリの[オンラインヘルプ](https://aka.ms/smahelp)はすぐにご利用いただけます。 IT 担当者は、次の問題について認識しておく必要があります。
  
- ユーザーが[ネットワーク要件](meetings-clients.md#Network)を満たすように構成されていないネットワーク上にいる場合は、多くのアプリ機能が機能しないことや、会議に接続できない場合があります。
    
- ユーザーによっては、アプリをインストールするためのアクセス許可が無効になっている企業管理のコンピューターが存在する場合があります。 これらのユーザーの場合、どちらのアプリもオプションではありませんが、[スマートフォン](https://products.office.com/skype-for-business/download-app?tab=tabs-1)および[タブレット](https://products.office.com/skype-for-business/download-app?tab=tabs-2)ユーザーは、会議に参加するために使用できる安価なモバイルクライアントをインストールすることができます。
    
    その他のインストールの問題についても、[ヘルプトピック](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)で説明されています。 
    
- ユーザーが会議アプリを初めて実行したときに、ファイアウォール警告が表示されることがあります。 そのためには、ポートを開くことを求めるメッセージが表示されることがあります。これには、使用していないコンピューターで管理者特権が必要になることがあります。 アプリは引き続き機能し、ユーザーは要求されたポートを開くことを安全に拒否することができます。 
    
- IE が既定のブラウザーではない場合でも、Internet Explorer でフィルターを適用[せずに ActiveX を有効に](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)する必要があります。 Skype for Business Web App では、ActiveX コントロール (web アプリやその他のプログラムに追加機能を追加する小さなモジュール) は、音声、ビデオ、画面共有に必要です。
    
- Skype for Business Web App の一部の機能を正常に動作させるには、お使いのブラウザーでコンピューターまたはデバイスに[cookie を保存](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)できるようにする必要があります。
    
- 一部の Skype for Business Web App 機能を期待どおりに動作させるには、ブラウザーで JavaScript サポートを[有効](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)にする必要がある場合があります。
    
### <a name="aes-support"></a>AES のサポート 

Skype for Business Server 2015 CU5 の場合、AES は ASP.NET 4.6 ではサポートされていません。これにより、Skype 会議アプリを開始できない場合があります。 [ASP .net 4.5 による暗号化要件](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45)には、詳細が含まれています。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[Skype for Business Server で Web ダウンロード可能なクライアントを展開する](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリでサポートされているプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
