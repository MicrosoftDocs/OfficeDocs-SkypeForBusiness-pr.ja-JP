---
title: 会議クライアント用の計画 (Web アプリおよび会議アプリ)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: '概要: IT プロフェッショナルは、skype for business Server の計画中に Skype for Business Web App と Skype 会議アプリのサポート要件を確認する必要があります。 この記事はこれらのアプリのユーザーを対象にしていません。'
ms.openlocfilehash: a2bc418b9179a63452c5d4fdd1990676f9db4b14
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277315"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>会議クライアント用の計画 (Web アプリおよび会議アプリ)
 
**概要:** IT 担当者は、skype for business Server の計画中に Skype for Business Web App と Skype 会議アプリのサポート要件を確認する必要があります。 この記事はこれらのアプリのユーザーを対象にしていません。
  
Skype for Business Server を実装したら、組織のユーザーは展開プロセスの一環として Skype for Business クライアントをインストールしている可能性があります。 
  
後で、これらのユーザーは会議を作成して、組織外のユーザーを招待することができます。また、会議の出席者が Skype for Business クライアントのバージョンを持っていない可能性があります。 それらのユーザーが会議出席依頼の URL をクリックすると、クライアントが見つからないことが検出され、Skype for Business クライアントを使用していない出席者が会議に参加できるように、軽量の会議専用クライアントをダウンロードしてインストールするように求められます。
  
> [!NOTE]
> Skype for Business Web App と Skype 会議アプリは、Skype for Business を使わずに会議にログインしようとしている場合にのみ使用できます。 これらのアプリのユーザーヘルプは[https://aka.ms/smahelp](https://aka.ms/smahelp)、です。 
  
> [!NOTE]
> Skype for Business Web App または Skype 会議アプリをインストールすることはできませんが、[スマートフォン](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)や[タブレット](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)ユーザーが、会議に参加するために使用できる安価なモバイルクライアントをインストールできる場合があります。
  
既定では、会議をホストしているサーバーは、Skype for Business Web App をダウンロードしてインストールし、会議に参加するようにユーザーに指示します。 Skype for Business Web App はフロントエンドサーバーに保存され、会議の出席者に送信されます。 
  
Skype for Business Server の場合は、Skype 会議アプリ (Windows) と Skype for Business for Mac (Mac の場合) は、CU5 以降で始まる Skype for Business Web App の代わりとして提供されていますが、代替アプリには追加の構成が必要です。「skype[会議アプリを使用して skype For Business Web App を置き換える (オプション)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)」の説明を参照してください。  Skype 会議アプリと Skype for Business for Mac が有効になっている場合、ユーザーは、Skype for Business サーバーからではなく、Office 365 コンテンツ配信ネットワーク (CDN) から最新バージョンのアプリをダウンロードします。 Skype for Business Server 2019 の場合、Skype 会議アプリと Skype for Business for Mac を使用するのは唯一のオプションです。
  
Skype 会議アプリでは、Internet Explorer のユーザーにワンクリックで参加するなど、アプリをダウンロードしてインストールし、会議に参加するための、簡素化されたブラウザーエクスペリエンスを提供します。 Skype 会議アプリでは、信頼性と会議のエクスペリエンスを実現するために、Skype for Business Web App の機能も大きく向上しています。 
  
> [!NOTE]
> Skype for Business Server 2015 CU5 以降以降のバージョンでは、Skype for business Online を使って会議を開催すると、クライアントのユーザーが Skype for Business Web App に送信されなくなり、skype 会議アプリ (Windows) または Skype for Business for Mac (Mac) が送信されます。 Skype for Business Server 2015 CU5 以降以降では、skype[会議アプリで skype For Business Web app の置き換えを有効](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)にした場合 (オプション)、クライアント数が Skype For Business web app ではなく、Skype 会議アプリまたは Skype for Business for Mac に送信されます。 
  
## <a name="software-requirements"></a>ソフトウェア要件
<a name="OS-Browser"> </a>

Skype for Business Web App を使用するには、次のサポートされているオペレーティングシステムとブラウザーの組み合わせのいずれかをユーザーが使用している必要があります。 
  
**Skype for Business Web App のオペレーティングシステムとブラウザーの最小サポート**

| オペレーティング システム | Edge | 32 ビット版と 64 ビット版の Internet Explorer 11 以降 | 32および64ビットの Internet Explorer 10 以降 | 32および64ビット Internet Explorer 9 以降 | Safari 6.2.8 の32および64ビットバージョン (8.x) | Chrome 18.x 以降の32および64ビットバージョン |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |はい  <br/> |あり  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |はい & # x2778; <br/> |
|Windows 8.1 & # x2776; <br/> |該当なし  <br/> |はい  <br/> |N/A  <br/> |N/A  <br/> |N/A <br/> |はい & # x2778; <br/> |
|Windows 8 (Intel ベース) & # x2776; <br/> |N/A  <br/> |該当なし  <br/> |はい  <br/> |N/A <br/> |N/A  <br/> |はい & # x2778; <br/> |
|Windows 7 SP1 & # x2777 <br/> |該当なし  <br/> |はい  <br/> |いいえ  <br/> |いいえ  <br/> |該当なし <br/>|はい & # x2778; <br/> |
|Windows Server 2008 R2 SP1 & # x2777 <br/> |該当なし  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |N/A <br/>|はい & # x2778; <br/> |
|macOS 10.8 以降 (Intel ベース) & # x2777 <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |該当なし  <br/> |はい  <br/> |はい <br/> |
   
&#x2776;Skype for Business Web App browser プラグインには、コンピューターベースの音声、ビデオ、共有、進行中の画面共有などの機能を使用するための特定の共有プラグインが必要です。 会議出席者は、会議に参加するとき、またはこれらの機能のいずれかを開始したときに、共有プラグインをインストールするオプションを提供します。 Windows 8 および Windows 8.1 では、Internet Explorer 10 または Internet Explorer 11 を実行している場合にのみ、共有プラグインをインストールできます。 これらの機能は、デスクトップ以外のバージョンの Internet Explorer 10 および11では使用できません。 Firefox および Safari バージョン12.0 以降はサポートされなくなりましたのでご注意ください。
  
&#x2777;サポートされている Windows 7、Windows Server 2008 R2、Macintosh オペレーティングシステムでは、コンピューターベースの音声、ビデオ、アプリケーションの表示、アプリケーション共有、デスクトップ表示、デスクトップ共有などのすべての機能を利用できます。 これらの機能を使用するには、画面の指示に従ってプラグインをインストールする必要があります。 Mac OS X バージョン10.7 はサポートされなくなったことに注意してください。
  
&#x2778;Windows の Chrome から Web アプリにアクセスすると、埋め込まれた Internet Explorer フレームに Web アプリを読み込む小さなプログラムが起動します。 Web App を適切に読み込むには、サポートされているいずれかのバージョンの Internet Explorer をインストールしておく必要があります。
  
> [!NOTE]
> Office 365 ユーザーは、Skype for Business で Internet Explorer 10 以降を使用できます。 
  
### <a name="skype-meetings-app"></a>Skype 会議アプリ

Skype 会議アプリは、Windows 10、Windows 8.1、Windows 8、Windows 7 を搭載したコンピュータで、32と64ビットの Internet Explorer 11 以降がインストールされているコンピューターで実行されます。 
  
その他の依存関係については、「 [Skype 会議アプリでサポートされているプラットフォーム](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)」を参照してください。
  
### <a name="skype-for-business-for-mac"></a>Skype for Business for Mac

Skype for Business for Mac は、macOS バージョン10.8 以降を搭載したコンピュータで動作します。 

## <a name="hardware-requirements"></a>ハードウェア要件
<a name="OS-Browser"> </a>

コンピューターのハードウェア要件はオペレーティング システムとブラウザーによって決まります。 音声機能とテレフォニー機能には、コンピューターと互換性のあるマイクおよびスピーカー、マイク付きヘッドセット、または同等のデバイスが必要です。 ビデオ機能には、コンピューターと互換性のあるビデオ デバイスが必要です。 ビデオハードウェアサポートと想定されるビデオ品質の詳細については、「 [Skype For business クライアントのビデオ解像度](video-resolutions.md)」を参照してください。
  
## <a name="network-requirements"></a>ネットワーク要件
<a name="Network"> </a>

Skype for Business Web App または Skype 会議アプリのユーザーに会議の接続の問題が発生した場合、 [office 365 の url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)で説明されているように、office 365 をサポートするように組織のネットワークインフラストラクチャが構成されていない可能性があります。 これは、会議が Skype for Business Online または Skype for Business Server のユーザーによって作成された場合に発生します。 
  
ユーザーがネットワーク上に存在し、構成が記載どおりに行われていない場合、多くのアプリの機能が機能したりしなかったりする可能性があり、会議に接続することがまったくできない場合があります。
  
## <a name="supported-meetings-features"></a>サポートされる会議機能
<a name="BKMK_Conferencing"> </a>

次の表は、Skype for Business クライアント、Skype for Business Web App、Skype 会議アプリ、Lync Web App のユーザーが利用できる会議機能を比較したものです。 機能の比較のために、lync Web App が一覧表示されています。ユーザーは、会議が Lync 2013 サーバーでホストされている場合にのみ Lync Web App をダウンロードして使用することになります。

| 機能 | Skype for Business 2016 または2019クライアント | Mac 版 Skype for Business クライアント | Skype 会議アプリ | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加  <br/> |&#x2714;|&#x2714;|&#x2714;(プラグインが必要です)  <br/> |&#x2714;(プラグインが必要です)  <br/> |&#x2714;(プラグインが必要です)  <br/> |
|ビデオの追加  <br/> |&#x2714;|&#x2714;|&#x2714;(プラグインが必要です)  <br/> |&#x2714;(プラグインが必要です)  <br/> |&#x2714;(プラグインが必要です)  <br/> |
|オーディオを認証済み参加者の電話に切り替え  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|オーディオをゲスト参加者の電話に切り替え  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|マルチパーティのビデオの表示 (ギャラリー ビュー)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオベースの画面共有  <br/> |&#x2714;|&#x2714; <br/> |& # x2714; (表示のみ)  <br/> |||
|会議内発表者コントロールの使用  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|詳細な会議参加者一覧へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM メッセージを「重要度 - 高」として設定  <br/> |&#x2714;|||||
|デスクトップの共有 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714;(プラグインが必要です)  <br/> |&#x2714;(プラグインが必要です)  <br/> |&#x2714;(プラグインが必要です)  <br/> |
|プログラムの共有 (有効な場合)  <br/> |&#x2714;||& # x2714; (Windows のみ)プラグインが必要です)  <br/> |& # x2714; (Windows のみ)プラグインが必要です)  <br/> |& # x2714; (Windows のみ)プラグインが必要です)  <br/> |
|他のユーザーの共有デスクトップまたはプログラムを制御する  <br/> |&#x2714;||&#x2714;(&#x2776;Windows のみ。プラグインが必要です)  <br/> |&#x2714;(&#x2776;Windows のみ。プラグインが必要です)  <br/> |&#x2714;(&#x2776;Windows のみ。プラグインが必要です)  <br/> |
|別のユーザーによる共有デスクトップまたはプログラムの制御の許可  <br/> |&#x2714;|||||
|匿名参加者の追加 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|名前で参加者を招待  <br/> |&#x2714;|&#x2714;||||
|電話番号で参加者を招待  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|メールで参加者を招待  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|ダイヤルイン音声会議の使用  <br/> |&#x2714;&#x2777; |&#x2714;&#x2777; |&#x2714;&#x2777; |&#x2714;&#x2777; |&#x2714;&#x2777; |
|今すぐミーティングによる会議の開始  <br/> |&#x2714;|&#x2714;||||
|会議のレコーディング  <br/> |&#x2714;|||||
|添付ファイルの追加とダウンロード  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイルの追加と発表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイル内の移動  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote 会議ノートの追加と編集  <br/> |&#x2714;||編集のみ (追加不可)  <br/> |編集のみ (追加不可)  <br/> |編集のみ (追加不可)  <br/> |
|ホワイトボードの使用  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|投票の実行  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|他のユーザーと共有するファイルをアップロードする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|会議をスケジュールする  <br/> |Outlook または Skype for Business Web Scheduler  <br/> |Outlook または Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |
|Q&a&amp;マネージャー  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|出席者のビデオを無効にする  <br/> |&#x2714;|||||
|会議のインスタント メッセージを無効にする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|参加者をミュートにする  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|全員を出席者にする  <br/> |&#x2714;|||||
|Skype 会議ブロードキャストを実施する  <br/> |&#x2714;|||||
   
 &#x2776; 参加者は、Skype for Business for Mac、Lync for Mac 2011、Communicator for Mac 2011 ユーザーが共有しているデスクトップを制御することはできません。 これは、OSX の Skype for Business Web App でも機能しません。
  
 &#x2777; Skype for Business Online の場合、この機能を使用するには、Microsoft PSTN 会議、Exchange ユニファイドメッセージング、またはサードパーティの電話会議プロバイダーが必要です。
  
 &#x2778; Lync for Mac 2011 クライアントは、Skype for Business Web App によって会議で共有されている場合、Microsoft Office 2013 PowerPoint プレゼンテーションを表示することはできません。
  
## <a name="known-issues-and-troubleshooting"></a>既知の問題とトラブルシューティング
<a name="BKMK_Conferencing"> </a>

エンドユーザーの場合、これらのアプリの[オンラインヘルプ](https://aka.ms/smahelp)はすぐに利用できます。 IT プロフェッショナルは、次の問題について認識する必要があります。
  
- ユーザーがネットワーク上に存在し、[ネットワーク要件](meetings-clients.md#Network)を満たすように構成されていない場合、多くのアプリの機能が機能したりしなかったりする可能性があり、会議に接続することがまったくできない場合があります。
    
- 一部のユーザーが、アプリをインストールするためのアクセス許可が無効化されている、会社管理のコンピューターを使用している場合があります。 これらのユーザーの場合、どちらのアプリもオプションではありませんが、[スマートフォン](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)や[タブレット](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)ユーザーが、会議に参加するために使用できる低コストのモバイルクライアントをインストールできる場合があります。
    
    その他のインストールの問題についても、[ヘルプトピック](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)をご覧ください。 
    
- ユーザーが会議アプリを初めて実行したときに、ファイアウォールの警告が表示される場合があります。 操作環境を最適化するためにポートを開くかどうかを確認するメッセージが表示されることがあります。これには、使用していないコンピューターで管理者特権が必要になることがあります。 アプリは引き続き機能する必要があり、要求されたポートを開くためにユーザーは安全に拒否することができます。 
    
- Internet Explorer では、Internet Explorer で[フィルターを使わずに ActiveX を有効に](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)する必要があります。これは、IE が既定のブラウザーではない場合でも可能です。 Skype for Business Web App では、音声、ビデオ、画面の共有のために、ActiveX コントロール (web アプリまたは他のプログラムに機能を追加する小さなモジュール) が必要になります。
    
- Skype for Business Web App の一部の機能を正しく動作させるには、お使いのコンピューターまたはデバイスに[cookie を保存](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)するようにブラウザーを設定する必要があります。
    
- 一部の Skype for Business Web App の機能が予期したとおりに動作するためには、ブラウザーで JavaScript のサポートを[有効](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)にする必要がある場合があります。
    
### <a name="aes-support"></a>AES サポート 

Skype for Business Server 2015 CU5 以降の場合、AES は ASP.NET 4.6 ではサポートされていないため、Skype 会議アプリの起動が失敗することがあります。 [ASP .net 4.5 に基づく暗号化の要件](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45)について詳しく説明します。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[Skype for Business Server で Web ダウンロード可能なクライアントを展開する](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリでサポートされるプラットフォーム](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
