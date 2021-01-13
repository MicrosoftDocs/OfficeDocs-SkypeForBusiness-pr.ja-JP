---
title: 会議クライアント用の計画 (Web アプリおよび会議アプリ)
ms.author: v-cichur
author: cichur
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
description: '概要: IT 担当者は、Skype for Business Server の計画時に、Skype for Business Web App と Skype 会議アプリのサポート要件を確認する必要があります。 この記事は、これらのアプリのユーザー向けではありません。'
ms.openlocfilehash: 4956a11c0ed163cbe50c49233e9aa05a0fbbd872
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826017"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>会議クライアント用の計画 (Web アプリおよび会議アプリ)
 
**概要:** IT 担当者は、Skype for Business Server の計画時に、Skype for Business Web App と Skype 会議アプリのサポート要件を確認する必要があります。 この記事は、これらのアプリのユーザー向けではありません。
  
Skype for Business Server を実装すると、組織のユーザーは、展開プロセスの一部として Skype for Business クライアントがインストールされている可能性があります。 
  
これらのユーザーは後で会議を作成し、組織外のユーザーを招待できます。また、これらの会議の招待者には Skype for Business クライアントのバージョンが存在しない場合があります。 これらのユーザーが会議の招待の URL をクリックすると、クライアントの不足が検出され、Skype for Business クライアントがない招待者は、会議に参加できるよう、会議専用の軽量なクライアントをダウンロードしてインストールする必要があります。
  
> [!NOTE]
> Skype for Business Web App と Skype 会議アプリは、Skype for Business を使用せずに会議にログインしようとするときにのみ利用できます。 これらのアプリのユーザー ヘルプは次のページです [https://aka.ms/smahelp](https://aka.ms/smahelp) 。 
  
> [!NOTE]
> Skype for Business Web App または Skype 会議アプリをプレインストールすることはできません[](https://products.office.com/skype-for-business/download-app?tab=tabs-1)が、スマートフォン[](https://products.office.com/skype-for-business/download-app?tab=tabs-2)とタブレットのユーザーは、会議に参加するために使用できる安価なモバイル クライアントをインストールできる場合があります。
  
既定では、会議をホストしているサーバーは、会議に参加するために Skype for Business Web App をダウンロードしてインストールする指示をユーザーに提供します。 Skype for Business Web App はフロントエンド サーバーに保存され、会議の出席者に送信されます。 
  
Skype for Business Server の場合、Skype 会議アプリ (Windows) と Skype for Business for Mac (Mac) は、CU5 で始まる Skype for Business Web App の代替として利用できますが、代替アプリを提供するには [、「Skype 会議](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)アプリで Skype for Business Web App を置き換える (オプション)」で説明されている追加の構成が必要です。 Skype 会議アプリと Skype for Business for Mac が有効になっている場合、ユーザーは Skype for Business サーバーからではなく、Microsoft 365 または Office 365 コンテンツ配信ネットワーク (CDN) から最新バージョンのアプリをダウンロードします。 Skype for Business Server 2019 では、Skype 会議アプリと Skype for Business for Mac の使用が唯一のオプションです。
  
Skype 会議アプリは、アプリをダウンロードしてインストールし、会議に参加するための簡素化されたブラウザー エクスペリエンスを提供します。たとえば、ユーザーが 1 回クリックで会議に参加Internet Explorer。 また、Skype 会議アプリは、信頼性と会議エクスペリエンスのために Skype for Business Web App に対して多くの改善を行いました。 
  
> [!NOTE]
> Skype for Business Server 2015 CU5 以降では、Skype for Business Online を使用して開催された会議は、クライアントレス ユーザーに Skype for Business Web App を送信しなくなりました。代わりに、Skype 会議アプリ (Windows) または Skype for Business for Mac (Mac) が送信されます。 Skype for Business Server 2015 CU5 以降では、Skype 会議アプリを有効にして Skype for Business Web App を置き換 [える場合 (オプション)、](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)クライアントレス ユーザーには Skype for Business Web App ではなく Skype 会議アプリまたは Skype for Business for Mac が送信されます。 
  
## <a name="software-requirements"></a>ソフトウェア要件
<a name="OS-Browser"> </a>

Skype for Business Web App を使用するには、次のオペレーティング システムとブラウザーの組み合わせがサポートされている必要があります。 
  
**Skype for Business Web App のオペレーティング システムと最小ブラウザー サポート**

| オペレーティング システム | Edge | 32 ビットおよび 64 ビット Internet Explorer 11 以降 | 32 ビットおよび 64 ビット Internet Explorer 10 以降 | 32 ビットおよび 64 ビットInternet Explorer 9以降 | 32 ビット版および 64 ビット版の Safari 6.2.8 - 11.X | 32 ビット版および 64 ビット版の Chrome 18.X 以降 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |はい  <br/> |必要  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |はい&#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |該当なし  <br/> |はい  <br/> |N/A  <br/> |N/A  <br/> |N/A <br/> |はい&#x2778; <br/> |
|Windows 8 (Intel ベース) &#x2776; <br/> |N/A  <br/> |N/A  <br/> |はい  <br/> |N/A <br/> |N/A  <br/> |はい&#x2778; <br/> |
|Windows 7 SP1 &#x2777; <br/> |該当なし  <br/> |必要  <br/> |いいえ  <br/> |いいえ  <br/> |該当なし <br/>|はい&#x2778; <br/> |
|WINDOWS SERVER 2008 R2 SP1 を使用&#x2777; <br/> |該当なし  <br/> |はい  <br/> |はい  <br/> |必要  <br/> |該当なし <br/>|はい&#x2778; <br/> |
|macOS 10.8 以降 (Intel ベース) &#x2777; <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |はい  <br/> |必要 <br/> |
   
&#x2776; Skype for Business Web App ブラウザー プラグインでは、コンピューター ベースの音声、ビデオ、共有、および継続的な画面共有などの機能の表示を使用するために、特定の共有プラグインが必要です。 会議の出席者には、会議に参加するときに、またはこれらの機能のいずれかを開始するときに、共有プラグインをインストールするオプションが提供されます。 Windows 8 Windows 8.1 では、デスクトップ用に Internet Explorer 10 または Internet Explorer 11 を実行している場合にのみ、共有プラグインをインストールできます。 これらの機能は、デスクトップ以外のバージョンの Internet Explorer 10 および 11 では使用できません。 Firefox および Safari バージョン 12.0 以降はサポートされなくなった点に注意してください。
  
&#x2777;サポートされている Windows 7、Windows Server 2008 R2、Macintosh オペレーティング システムでは、コンピューター ベースの音声、ビデオ、アプリケーション表示、アプリケーション共有、デスクトップ表示、デスクトップ共有など、すべての機能を利用できます。 これらの機能を使用するには、メッセージが表示されたらプラグインをインストールする必要があります。 Mac OS X バージョン 10.7 はサポートされなくなった点に注意してください。  また、Web アプリは OS X 10.15 以降にはインストールされない点にも注意してください。  今後の匿名参加シナリオをサポートする Skype for Business for Mac の最新バージョンを使用することをお勧めします。
  
&#x2778; Chrome から Web アプリにアクセスすると、埋め込まれたフレームに Web アプリを読み込む小さなInternet Explorerされます。 このプログラムを実行するには、Web App が正しく読み込Internet Explorerサポートされているバージョンの 1 つがインストールされている必要があります。
  
> [!NOTE]
> Microsoft 365 および Office 365 ユーザーは、Skype for Business Internet Explorer 10 以降を使用できます。 
  
### <a name="skype-meetings-app"></a>Skype 会議アプリ

Skype 会議アプリは、32 ビットおよび 64 ビットの Internet Explorer 11 以降がインストールされた Windows 10、Windows 8.1、Windows 8、Windows 7 を使用するコンピューターでアプリとして実行されます。 
  
その他の依存関係については [、Skype 会議アプリでサポートされているプラットフォームを参照してください。](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business for Mac

Skype for Business for Mac は、macOS バージョン 10.8 以降を使用しているコンピューターで実行されます。 

## <a name="hardware-requirements"></a>ハードウェア要件
<a name="OS-Browser"> </a>

コンピューターのハードウェア要件は、オペレーティング システムとブラウザーによって決まります。 音声およびテレフォニー機能には、マイクとスピーカー、マイク付きヘッドセット、またはコンピューターと互換性のある同等のデバイスが必要です。 ビデオ機能には、コンピューターと互換性のあるビデオ デバイスが必要です。 ビデオ ハードウェア サポートと予想されるビデオ品質の詳細については、Skype for Business クライアントのビデオ解像度 [を参照してください](video-resolutions.md)。
  
## <a name="network-requirements"></a>ネットワーク要件
<a name="Network"> </a>

Skype for Business Web App または Skype 会議アプリのユーザーが会議の接続の問題を経験した場合、組織のネットワーク インフラストラクチャが Office 365 URL と IP アドレス範囲で説明するように [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)をサポートするように構成されていない可能性があります。 これは、Skype for Business Online または Skype for Business Server のユーザーが会議を作成したかどうかです。 
  
ユーザーが上記のように構成されていないネットワーク上にある場合、多くのアプリ機能が機能する場合と機能しない場合があります。また、会議に接続できない場合があります。
  
## <a name="supported-meetings-features"></a>サポートされる会議機能
<a name="BKMK_Conferencing"> </a>

次の表は、Skype for Business クライアント、Skype for Business Web App、Skype 会議アプリ、および Lync Web App のユーザーが使用できる会議機能を比較しています。 Lync Web App は機能の比較を目的としてリストされています。ユーザーは、会議が Lync 2013 サーバーでホストされている場合にのみ、Lync Web App をダウンロードして使用します。

| 機能 | Skype for Business 2016 または 2019 クライアント | Mac クライアント上の Skype for Business | Skype 会議アプリ | Skype for Business の Web アプリ | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|ビデオの追加  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|認証された参加者の電話にオーディオを切り替える  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ゲスト参加者の電話にオーディオを切り替える  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|マルチパーティビデオを表示する (ギャラリー ビュー)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオベースの画面共有  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(表示のみ)  <br/> |||
|会議内発表者コントロールの使用  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|詳細な会議名簿へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM メッセージの重要度を高く設定する  <br/> |&#x2714;|||||
|デスクトップの共有 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |&#x2714; (プラグインが必要)  <br/> |
|プログラムの共有 (有効な場合)  <br/> |&#x2714;||&#x2714; (Windows の場合のみ、プラグインが必要)  <br/> |&#x2714; (Windows の場合のみ、プラグインが必要)  <br/> |&#x2714; (Windows の場合のみ、プラグインが必要)  <br/> |
|別のユーザーの共有デスクトップまたはプログラムを制御する  <br/> |&#x2714;||&#x2714; (&#x2776; Windows のみ。プラグインが必要)  <br/> |&#x2714; (&#x2776; Windows のみ。プラグインが必要)  <br/> |&#x2714; (&#x2776; Windows のみ。プラグインが必要)  <br/> |
|別のユーザーが共有デスクトップまたはプログラムを制御する  <br/> |&#x2714;|||||
|匿名参加者の追加 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参加者を名前で招待する  <br/> |&#x2714;|&#x2714;||||
|電話番号で参加者を招待する  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|電子メールで参加者を招待する  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|ダイヤルイン オーディオ会議を使用する  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|今すぐミーティングを開始する  <br/> |&#x2714;|&#x2714;||||
|会議を記録する  <br/> |&#x2714;|||||
|添付ファイルの追加とダウンロード  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイルの追加と提示  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイルを移動する  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote 会議メモを追加および編集する  <br/> |&#x2714;||編集のみ (追加しない)  <br/> |編集のみ (追加しない)  <br/> |編集のみ (追加しない)  <br/> |
|ホワイトボードの使用  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|投票の実行  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|ファイルをアップロードして他のユーザーと共有する  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|会議または電話会議の予約  <br/> |Outlook または Skype for Business Web スケジューラ  <br/> |Outlook または Skype for Business Web スケジューラ  <br/> |Skype for Business Web スケジューラー  <br/> |Skype for Business Web スケジューラー  <br/> |Skype for Business Web スケジューラー  <br/> |
|Q &amp; A マネージャー  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|出席者のビデオを無効にする  <br/> |&#x2714;|||||
|会議 IM を無効にする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|対象ユーザーをミュートする  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|すべてのユーザーを出席者にする  <br/> |&#x2714;|||||
|Skype 会議ブロードキャストを作成する  <br/> |&#x2714;|||||
   
 &#x2776;参加者は、Skype for Business for Mac、Lync for Mac 2011、またはユーザーが共有するデスクトップCommunicator for Mac 2011制御できない。 これは、Max OSX 上の Skype for Business Web App でも機能しません。
  
 &#x2777; Skype for Business Online の場合、この機能には Microsoft PSTN 会議、Exchange ユニファイド メッセージング、またはサードパーティの電話会議プロバイダーが必要です。
  
 &#x2778; Lync for Mac 2011 クライアントは、Skype for Business Web App で会議で共有されている Microsoft Office 2013 PowerPoint プレゼンテーションを表示できません。
  
## <a name="known-issues-and-troubleshooting"></a>既知の問題とトラブルシューティング
<a name="BKMK_Conferencing"> </a>

エンドユーザーは、これらの [アプリのオンライン](https://aka.ms/smahelp) ヘルプをすぐに利用できます。 IT 担当者は、次の問題に注意する必要があります。
  
- ユーザーがネットワーク要件を満たしていないネットワーク上にある場合[](meetings-clients.md#Network)、多くのアプリ機能が機能する場合と機能しない場合があります。また、会議に接続できない場合があります。
    
- 一部のユーザーは、アプリをインストールするためのアクセス許可が無効になっている企業管理のコンピューターを持っている場合があります。 これらのユーザーの場合、どちらのアプリもオプションではありません。ただし、[スマートフォン](https://products.office.com/skype-for-business/download-app?tab=tabs-1)と[](https://products.office.com/skype-for-business/download-app?tab=tabs-2)タブレットのユーザーは、会議に出席するために使用できる安価なモバイル クライアントをインストールできる場合があります。
    
    その他のインストールに関する問題については、ヘルプ トピックでも [説明されています](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)。 
    
- 会議アプリを初めて実行すると、ファイアウォールの警告が表示される場合があります。 エクスペリエンスを最適化するためにポートを開くというメッセージが表示される場合があります。また、この操作を行う場合は、ユーザーが持てない可能性があるコンピューターに対する管理者特権が必要になる場合があります。 アプリは引き続き機能し、ユーザーは要求されたポートを開くことを安全に拒否できます。 
    
- IE が既定 [ActiveXブラウザーではない場合](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) でも、Internet Explorerでフィルターを適用せずに有効にする必要があります。 Skype for Business Web App では、ActiveX コントロール (Web アプリまたは他のプログラムに追加機能を追加する小さなモジュール) は、オーディオ、ビデオ、画面共有に必要です。
    
- Skype for Business Web App の一部の機能が正しく動作[](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)するには、ブラウザーがコンピューターまたはデバイスに Cookie を保存できる必要があります。
    
- 一部の Skype for Business Web App 機能が期待通り動作するには、ブラウザーで [JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) サポートを有効にする必要がある場合があります。
    
### <a name="aes-support"></a>AES サポート 

Skype for Business Server 2015 CU5 では、AES は ASP.NET 4.6 ではサポートされていません。このため、Skype 会議アプリの起動が失敗する可能性があります。 [ASP .NET 4.5 による暗号化要件には、](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) より詳細な情報があります。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[Skype for Business Server で Web ダウンロード可能なクライアントを展開する](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリでサポートされるプラットフォーム](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
