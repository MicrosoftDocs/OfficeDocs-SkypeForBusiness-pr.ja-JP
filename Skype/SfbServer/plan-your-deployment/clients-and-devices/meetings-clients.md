---
title: 会議クライアント用の計画 (Web アプリおよび会議アプリ)
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: '概要: IT 担当者は、会議の計画中に、Skype for Business Web アプリおよび Skype 会議アプリのサポート要件を確認Skype for Business Server。 この記事は、これらのアプリのユーザー向けではありません。'
ms.openlocfilehash: bf6eb62291309500c942e83c41e898b5a4d25531
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395159"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>会議クライアント用の計画 (Web アプリおよび会議アプリ)
 
**概要:** IT 担当者は、会議の計画中に、Skype for Business Web アプリおよびSkype会議アプリのサポート要件を確認Skype for Business Server。 この記事は、これらのアプリのユーザー向けではありません。
  
組織のユーザーは、Skype for Business Server実装すると、展開プロセスの一部としてSkype for Businessクライアントがインストールされている可能性があります。 
  
その後、これらのユーザーは会議を作成し、組織外からユーザーを招待できます。また、それらの会議の招待者にはクライアントのバージョンSkype for Businessがあります。 これらのユーザーが会議出席招待の URL をクリックすると、クライアントの不足が検出され、Skype for Business クライアントのない招待者は、会議に参加できるよう、軽量で会議専用のクライアントをダウンロードしてインストールする必要があります。
  
> [!NOTE]
> 会議Skype for Business Web アプリおよびSkypeは、会議にアクセスせずに会議にログインしようとするときにのみSkype for Business。 これらのアプリのユーザー ヘルプは .[https://aka.ms/smahelp](https://aka.ms/smahelp) 
  
> [!NOTE]
> Skype for Business Web アプリ または Skype Meetings App を事前インストールすることはできませんが、スマートフォンとタブレットのユーザーは、会議に出席するために[](https://products.office.com/skype-for-business/download-app?tab=tabs-1)使用できる安価[](https://products.office.com/skype-for-business/download-app?tab=tabs-2)なモバイル クライアントをインストールできる場合があります。
  
既定では、会議をホストしているサーバーは、会議に参加するためにユーザーにSkype for Business Web アプリインストールを指示します。 このSkype for Business Web アプリはフロントエンド サーバーに保存され、会議出席者に送信されます。 
  
たとえばSkype for Business Server会議Skype (Windows) と Skype for Business for Mac (Mac) は、Skype for Business Web アプリ の代替として使用Skype for Business Web アプリ CU5 から始まるが、置換アプリを提供するには、「会議アプリを有効にする (省略可能)Skype」で説明されている追加Skype for Business Web アプリ[必要があります](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)。 会議Skypeおよび Skype for Business for Mac が有効になっている場合、ユーザーは最新バージョンのアプリを Microsoft 365 または Office 365 Content Delivery Network (CDN) からダウンロードします。Skype for Businessサーバー。 2019 Skype for Business Server、会議アプリと会議Skypeを使用Skype for Business for Mac唯一のオプションです。
  
Skype会議アプリは、アプリをダウンロードしてインストールし、会議に参加するための簡略化されたブラウザー エクスペリエンスを提供します。たとえば、Internet Explorer のユーザーに対する 1 回のクリック参加を含む。 Skype会議アプリには、信頼性と会議のSkype for Business Web アプリに関する多くの改善点があります。 
  
> [!NOTE]
> Skype for Business Server 2015 CU5 以降では、Skype for Business Online を使用して開催された会議は、Skype for Business Web アプリ のクライアントレス ユーザーを送信しなくなりました。代わりに Skype Meetings App (Windows) またはSkype for Business for Mac (Mac 上) 2015 Skype for Business Server CU5 以降の場合、[Skype 会議アプリで Skype for Business Web アプリ (オプション)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable) を置き換えるを有効にした場合、クライアントレス ユーザーは Skype Meetings App またはSkype for Business for Macの代わりにSkype for Business Web アプリ。 
  
## <a name="software-requirements"></a>ソフトウェア要件
<a name="OS-Browser"> </a>

このアプリケーションをSkype for Business Web アプリ、ユーザーはサポートされているオペレーティング システムとブラウザーの組み合わせのいずれかを持っている必要があります。 
  
**オペレーティング システムとブラウザーの最小サポートSkype for Business Web アプリ**

| オペレーティング システム | Edge | 32 ビットおよび 64 ビット Internet Explorer 11 以降 | 32 ビットおよび 64 ビットInternet Explorer 10以降 | 32 ビットおよび 64 ビットInternet Explorer 9以降 | 32 ビット版と 64 ビット版の Safari 6.2.8 ~ 11.X | 32 ビット版および 64 ビット版の Chrome 18.X 以降 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |はい  <br/> |はい  <br/> |該当なし  <br/> |該当なし  <br/> |該当なし  <br/> |はい &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |該当なし  <br/> |はい  <br/> |該当なし  <br/> |該当なし  <br/> |該当なし <br/> |はい &#x2778; <br/> |
|Windows 8 (Intel ベース) &#x2776; <br/> |該当なし  <br/> |該当なし  <br/> |はい  <br/> |該当なし <br/> |該当なし  <br/> |はい &#x2778; <br/> |
|Windows 7 sp1 &#x2777; <br/> |該当なし  <br/> |はい  <br/> |不要  <br/> |不要  <br/> |該当なし <br/>|はい &#x2778; <br/> |
|Windows SP1 サーバー 2008 R2 &#x2777; <br/> |該当なし  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |該当なし <br/>|はい &#x2778; <br/> |
|macOS 10.8 以降 (Intel ベース) &#x2777; <br/> |該当なし  <br/> |該当なし  <br/> |該当なし  <br/> |該当なし  <br/> |はい  <br/> |はい <br/> |
   
&#x2776; Skype for Business Web アプリブラウザー プラグインでは、コンピューターベースの音声、ビデオ、共有、および継続的な画面共有などの機能の表示を使用するために、特定の共有プラグインが必要です。 会議出席者には、会議に参加するときに、またはこれらの機能のいずれかを開始するときに共有プラグインをインストールするオプションが与えられる。 デスクトップWindows 8 Windows 8.1、共有プラグインをインストールできるのは、デスクトップで Internet Explorer 10 または Internet Explorer 11 を実行している場合のみです。 これらの機能は、デスクトップ以外のバージョンの Internet Explorer 10 11 では使用できません。 Firefox および Safari バージョン 12.0 以降はサポートされなくなりました。
  
&#x2777; サポートされている Windows 7、Windows Server 2008 R2、Macintosh オペレーティング システムでは、コンピューターベースの音声、ビデオ、アプリケーションの表示、アプリケーション共有、デスクトップ表示、デスクトップ共有など、すべての機能を利用できます。 これらの機能を使用するには、プロンプトが表示されたらプラグインをインストールする必要があります。 Mac OS X バージョン 10.7 はサポートされなくなりました。  また、Web アプリは OS X 10.15 以降にインストールされない点にも注意してください。  今後の匿名参加シナリオをサポートする最新Skype for Business for Macを使用することをお勧めします。
  
&#x2778; Windows Chrome から Web アプリにアクセスすると、埋め込みアプリケーション フレームに Web アプリを読み込む小さなInternet Explorerされます。 このプログラムでは、Web アプリが正しく読み込まれるInternet Explorerサポートされているバージョンの 1 つをインストールする必要があります。
  
> [!NOTE]
> Microsoft 365およびOffice 365ユーザーは、Internet Explorer 10以降のユーザーを使用Skype for Business。 
  
### <a name="skype-meetings-app"></a>Skype 会議アプリ

Skype会議アプリは、Windows 10、Windows 8.1、Windows 8、Windows 7 を使用するコンピューターでアプリとして実行され、32 ビットおよび 64 ビット Internet Explorer 11 以降がインストールされています。 
  
その他の依存関係については、「会議アプリでサポート[されているプラットフォームSkype参照してください。](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business for Mac

Skype for Business for Mac macOS バージョン 10.8 以降を使用しているコンピューターで実行されます。 

## <a name="hardware-requirements"></a>ハードウェア要件
<a name="OS-Browser"> </a>

コンピューターのハードウェア要件は、オペレーティング システムとブラウザーによって決まります。 音声およびテレフォニー機能には、マイクとスピーカー、マイク付きヘッドセット、またはコンピューターと互換性のある同等のデバイスが必要です。 ビデオ機能には、コンピューターと互換性のあるビデオ デバイスが必要です。 ビデオ ハードウェアのサポートと予想されるビデオ品質の詳細については、「クライアント[のビデオSkype for Businessを参照してください](video-resolutions.md)。
  
## <a name="network-requirements"></a>ネットワーク要件
<a name="Network"> </a>

Skype for Business Web アプリ または Skype Meetings App のユーザーが会議の接続の問題を経験した場合、Office 365 [URL と IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) アドレス範囲で説明されているとおりに、組織のネットワーク インフラストラクチャが Office 365 をサポートするように構成されていない可能性があります。 これは、会議がオンラインまたはユーザーのユーザーによって作成されたSkype for Business場合Skype for Business Server。 
  
ユーザーが説明に従って構成されていないネットワーク上にある場合、多くのアプリ機能が機能する場合と機能しない場合があります。また、会議に接続できない場合があります。
  
## <a name="supported-meetings-features"></a>サポートされている会議機能
<a name="BKMK_Conferencing"> </a>

次の表は、クライアント、Skype for Business、Skype for Business Web アプリ、Skype Web アプリのユーザーが利用できる会議機能を比較します。 Lync Web App は機能比較の目的でリストされています。ユーザーは、会議が Lync 2013 サーバーでホストされている場合にのみ、Lync Web App をダウンロードして使用します。

| 機能/機能 | Skype for Business 2016 または 2019 クライアント | Skype for Business Mac クライアントでの設定 | Skype 会議アプリ | Skype for Business の Web アプリ | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|ビデオの追加  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|認証された参加者の電話にオーディオを切り替える  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ゲスト参加者の電話にオーディオを切り替える  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|マルチパーティ ビデオの表示 (ギャラリー ビュー)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオベースの画面共有  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(View-only)  <br/> |||
|会議内発表者コントロールの使用  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|詳細な会議名簿へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM メッセージの重要度を高く設定する  <br/> |&#x2714;|||||
|デスクトップの共有 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|プログラムの共有 (有効な場合)  <br/> |&#x2714;||&#x2714;(オンWindowsのみ。プラグインが必要)  <br/> |&#x2714;(オンWindowsのみ。プラグインが必要)  <br/> |&#x2714;(オンWindowsのみ。プラグインが必要)  <br/> |
|別のユーザーの共有デスクトップまたはプログラムを制御する  <br/> |&#x2714;||&#x2714; (&#x2776;オンWindowsのみ、プラグインが必要)  <br/> |&#x2714; (&#x2776;オンWindowsのみ、プラグインが必要)  <br/> |&#x2714; (&#x2776;オンWindowsのみ、プラグインが必要)  <br/> |
|別のユーザーに共有デスクトップまたはプログラムの制御を許可する  <br/> |&#x2714;|||||
|匿名参加者の追加 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参加者を名前で招待する  <br/> |&#x2714;|&#x2714;||||
|電話番号で参加者を招待する  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参加者をメールで招待する  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|ダイヤルイン オーディオ会議を使用する  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|会議を開始する  <br/> |&#x2714;|&#x2714;||||
|会議を記録する  <br/> |&#x2714;|||||
|添付ファイルの追加とダウンロード  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイルの追加と提示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft のファイルPowerPoint移動する  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|会議メモを追加OneNote編集する  <br/> |&#x2714;||編集のみ (追加しない)  <br/> |編集のみ (追加しない)  <br/> |編集のみ (追加しない)  <br/> |
|ホワイトボードの使用  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|投票の実行  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|アップロード共有するファイルを作成する  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|会議または電話会議の予約  <br/> |OutlookまたはSkype for Business Web スケジューラー  <br/> |OutlookまたはSkype for Business Web スケジューラー  <br/> |Skype for Business Web スケジューラー  <br/> |Skype for Business Web スケジューラー  <br/> |Skype for Business Web スケジューラー  <br/> |
|QA&amp; マネージャー  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|出席者ビデオを無効にする  <br/> |&#x2714;|||||
|会議 IM を無効にする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|対象ユーザーをミュートする  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|全員を出席者にする  <br/> |&#x2714;|||||
|会議Skypeブロードキャストを生成する  <br/> |&#x2714;|||||
   
 &#x2776;参加者は、Skype for Business for Mac、Lync for Mac 2011、または Mac 2011 ユーザー Communicator共有するデスクトップを制御できない。 これは、Max OSX 上のSkype for Business Web アプリも機能しません。
  
 &#x2777; オンラインSkype for Businessこの機能には、Microsoft PSTN 会議、Exchange ユニファイド メッセージング、またはサードパーティの電話会議プロバイダーが必要です。
  
 &#x2778; Lync for Mac 2011 クライアントは、Microsoft Office PowerPoint によって会議で共有されている場合、PowerPoint プレゼンテーションを表示Skype for Business Web アプリ。
  
## <a name="known-issues-and-troubleshooting"></a>既知の問題とトラブルシューティング
<a name="BKMK_Conferencing"> </a>

エンド ユーザー向けには、 [これらのアプリの](https://aka.ms/smahelp) オンライン ヘルプをすぐに利用できます。 IT 担当者は、次の問題に注意する必要があります。
  
- ユーザーがネットワーク要件を満たして構成されていないネットワーク上[](meetings-clients.md#Network)にある場合、多くのアプリ機能が機能する場合と機能しない場合があります。また、会議に接続できない場合があります。
    
- 一部のユーザーは、アプリをインストールする権限が無効になっている企業が管理するコンピューターを持っている場合があります。 これらのユーザーの場合、どちらのアプリもオプションではありません。スマートフォン[](https://products.office.com/skype-for-business/download-app?tab=tabs-1)とタブレットの[](https://products.office.com/skype-for-business/download-app?tab=tabs-2)ユーザーは、会議に出席するために使用できる安価なモバイル クライアントをインストールできる場合があります。
    
    その他のインストールの問題については、ヘルプ トピックでも [説明します](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)。 
    
- ユーザーが会議アプリを初めて実行すると、ファイアウォールの警告が表示される場合があります。 エクスペリエンスを最適化するためにポートを開くメッセージが表示される場合があります。また、この操作を行う場合は、持てない可能性があるコンピューターに対する管理者特権が必要になる場合があります。 アプリは引き続き機能し、ユーザーは要求されたポートを開くことを安全に拒否できます。 
    
- IE が[既定のActiveX場合でも、](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)Internet Explorerでフィルターを適用せずに有効になっている必要があります。 このSkype for Business Web アプリ、ActiveXアプリや他のプログラムに追加機能を追加する小さなモジュールである ActiveX コントロールは、オーディオ、ビデオ、画面の共有に必要です。
    
- ブラウザーの一部Skype for Business Web アプリ機能を正しく動作するには、ブラウザーがコンピューターまたはデバイスに [Cookie を保存](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)するようにする必要があります。
    
- 一部の機能が期待通り動作するには、ブラウザーで [JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) Skype for Business Web アプリする必要があります。
    
### <a name="aes-support"></a>AES サポート 

2015 Skype for Business Server CU5 の時点では、AES は ASP.NET 4.6 ではサポートされていません。これにより、Skype Meetings App の起動が失敗する可能性があります。 [4.5 の ASP.NET に関する暗号化](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) 要件の詳細が示されています。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[Web ダウンロード可能なクライアントを展開Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[会議アプリでサポートSkypeプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
