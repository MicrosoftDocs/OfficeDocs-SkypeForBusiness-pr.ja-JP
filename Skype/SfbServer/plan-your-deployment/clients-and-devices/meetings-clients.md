---
title: 会議クライアント用の計画 (Web アプリおよび会議アプリ)
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: '概要: IT プロフェッショナルは Skype ビジネス サーバーの計画中に、Skype のビジネス Web アプリケーションおよび Skype 会議アプリケーションのサポート要件を確認する必要があります。 この記事はこれらのアプリのユーザーを対象にしていません。'
ms.openlocfilehash: 6006bf1ca4b8ce63a662a1c55c79865097c86b18
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207364"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>会議クライアント用の計画 (Web アプリおよび会議アプリ)
 
**の概要:** IT プロフェッショナルは、Skype ビジネス サーバーの計画中に、Skype のビジネス Web アプリケーションおよび Skype 会議アプリケーションのサポート要件を確認する必要があります。 この記事はこれらのアプリのユーザーを対象にしていません。
  
ビジネス サーバーの Skype を実装した後、組織のユーザーはビジネスのクライアントの展開プロセスの一部としてインストールされている Skype をおそらくがあります。 
  
後で、そのユーザーは会議を作成し、組織の外部ユーザーを招待し、それらの会議の出席者で、Skype ビジネス クライアント用のすべてのバージョンがない可能性があります。 それらのユーザーは、会議出席依頼の URL をクリックして、クライアントがないことが検出され、せず、Skype クライアントのビジネスの招待者をダウンロードして会議に参加することができますので、会議専用の軽量なクライアントをインストールするように求められます。
  
> [!NOTE]
> ビジネス Web アプリケーションの Skype と Skype 会議アプリケーションには、せずに、ビジネスの Skype 会議にログインしようとしています。 これらのアプリケーションについては、ユーザーが、 [https://aka.ms/smahelp](https://aka.ms/smahelp)。 
  
> [!NOTE]
> 事前ビジネス Web アプリケーションや、Skype 会議アプリケーションのいずれかの Skype をインストールできませんが、[スマート フォン](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)や[タブレット](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)のユーザーは、ミーティングに参加するのには使用できる低コストのモバイル クライアントをインストールできる場合があります。
  
既定では、会議をホストしているサーバーはダウンロードし、ミーティングに参加する Web アプリケーションのビジネス用の Skype をインストールするユーザーを指示します。 ビジネス Web アプリケーションの Skype では、フロント エンド サーバーに格納され、会議の出席者に送信されます。 
  
ビジネス サーバーの Skype、Skype 会議のアプリケーション (Windows) でと Skype for Mac (Mac) でのビジネスの Skype の代わりに CU5 で始まるビジネス Web アプリケーションを利用可能なですが、交換用のアプリケーションを提供するには、追加構成が必要です。[Skype ビジネス Web アプリケーション (オプション) を置換する Skype 会議アプリケーションを有効にする](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)」に記載します。  会議アプリケーションの Skype と Skype for Mac のビジネスが有効な場合、Office 365 コンテンツ配信ネットワーク (CDN) からではなく、Skype をビジネスのサーバーのユーザーは、アプリケーションの最新バージョンをダウンロードします。 ビジネス サーバー 2019 の Skype、for Mac ビジネスの会議アプリケーションの Skype と Skype を使用しての唯一のオプションです。
  
Skype 会議アプリケーションは、ダウンロードし、アプリケーションをインストールして Internet Explorer のユーザーの 1 回のクリックの結合を含めて、会議に参加するための簡略化されたブラウザー エクスペリエンスを提供します。 Skype 会議アプリケーションも多くの改良、Skype 経由でビジネス Web アプリケーションの信頼性と会議の経験のため。 
  
> [!NOTE]
> Skype ビジネス サーバー 2015 CU5 またはそれ以降は、現在 Skype を使用してビジネスをオンラインに保持されている会議が不要になったユーザーに送信、クライアントレス、Skype ビジネス Web アプリケーションの代わりに送信されます (Windows) での Skype 会議アプリケーションまたはビジネス用の Skype for Mac (Mac) にします。 現在のビジネス サーバー 2015 CU5 以降、 [Skype のビジネス Web アプリケーション (オプション) を交換する Skype 会議アプリケーションを有効にする](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)、クライアントレスのユーザーは、Skype の会議アプリケーションを送信する場合、Skype または Skype for Mac ビジネス Web アプリケーションの Skype ではなくビジネスの。 
  
## <a name="software-requirements"></a>ソフトウェア要件
<a name="OS-Browser"> </a>

ビジネス Web アプリケーションでは、ユーザーは、Skype を使用するのには、次のいずれかでサポートされているオペレーティング システムとブラウザーの組み合わせです。 
  
**ビジネス Web アプリケーションの Skype のオペレーティング システムとブラウザーの最小サポートします。**

| オペレーティング システム | Edge | 32 ビット版と 64 ビット版の Internet Explorer 11 以降 | 32 ビットと 64 ビットの 10 またはそれ以降の Internet Explorer | 32 ビットと 64 ビットのまたはそれ以降の Internet Explorer 9 | Safari 6.2.8 の 11.X の 32 ビットおよび 64 ビット バージョン | 32 ビットと 64 ビットのクロムのバージョン 18.X またはそれ以降 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |はい  <br/> |あり  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |はい & #x 2778 です。 <br/> |
|Windows 8.1 & #x 2776。 <br/> |該当なし  <br/> |はい  <br/> |N/A  <br/> |N/A  <br/> |N/A <br/> |はい & #x 2778 です。 <br/> |
|Windows 8 (Intel ベース) & #x 2776。 <br/> |N/A  <br/> |該当なし  <br/> |はい  <br/> |N/A <br/> |N/A  <br/> |はい & #x 2778 です。 <br/> |
|Windows 7 の SP1 & #x 2777 です。 <br/> |該当なし  <br/> |はい  <br/> |いいえ  <br/> |いいえ  <br/> |該当なし <br/>|はい & #x 2778 です。 <br/> |
|Windows Server 2008 R2 の SP1 & #x 2777; と <br/> |該当なし  <br/> |はい  <br/> |はい  <br/> |あり  <br/> |N/A <br/>|はい & #x 2778 です。 <br/> |
|macOS 10.8 と後で (Intel ベース) & #x 2777 です。 <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |該当なし  <br/> |はい  <br/> |はい <br/> |
   
& #x 2776。ビジネス Web アプリケーションのブラウザー プラグインの Skype では、コンピューター ベースの音声、ビデオ、共有、共有の継続的な画面の表示およびその他の機能を使用する特定の共有プラグインが必要です。 会議の出席者には、共有プラグイン会議に参加するとき、またはこれらの機能の 1 つを開始するときのいずれかをインストールするオプションが与えられます。 Windows 8、および Windows 8.1 では、プラグインの共有インストールできますデスクトップ用 Internet Explorer 10 または 11 の Internet Explorer を実行している場合のみです。 これらの機能は、Internet Explorer 10 と 11 以外のデスクトップ バージョンをご利用いただけません。 Firefox および Safari バージョン 12.0 以降ではサポートされていません注意してください。
  
& #x 2777 です。サポートされている Windows 7、Windows Server 2008 R2、および Macintosh オペレーティング システムの場合、すべての機能があるコンピューター ベースの音声、ビデオ、アプリケーションの表示、アプリケーション共有、デスクトップの表示をするには、およびデスクトップの共有を含みます。 これらの機能を使用するにはプラグインが表示されたらインストールしてください。 10.7 の Mac OS X バージョンはサポートされていません注意してください。
  
& #x 2778 です。Windows 上のクロムから Web アプリケーションにアクセスすると、埋め込みの Internet Explorer のフレームで Web アプリケーションをロードする小さなプログラムが起動します。 Web App を適切に読み込むには、サポートされているいずれかのバージョンの Internet Explorer をインストールしておく必要があります。
  
> [!NOTE]
> Office 365 のユーザーは、ビジネスのため、Skype で 10 またはそれ以降の Internet Explorer を使用できます。 
  
### <a name="skype-meetings-app"></a>Skype 会議アプリ

Skype 会議アプリケーションは、Windows 10、Windows 8.1、Windows 8 の Windows 7 で 32 ビットおよび 64 ビット Internet Explorer 11 を使用してコンピューター上でアプリケーションとして実行または以降がインストールされています。 
  
その他の依存関係、 [Skype 会議アプリケーションでサポートされるプラットフォーム](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)を参照してください。
  
### <a name="skype-for-business-for-mac"></a>Skype for Mac のビジネスの

Skype for Mac のビジネスは、macOS 10.8 以降のバージョンを使用しているコンピューターで実行されます。 

## <a name="hardware-requirements"></a>ハードウェア要件
<a name="OS-Browser"> </a>

コンピューターのハードウェア要件はオペレーティング システムとブラウザーによって決まります。 音声機能とテレフォニー機能には、コンピューターと互換性のあるマイクおよびスピーカー、マイク付きヘッドセット、または同等のデバイスが必要です。 ビデオ機能には、コンピューターと互換性のあるビデオ デバイスが必要です。 ビデオ ハードウェアのサポートと必要なビデオの品質についての詳細については、 [Skype](video-resolutions.md)を参照してください。
  
## <a name="network-requirements"></a>ネットワーク要件
<a name="Network"> </a>

接続の問題を満たすビジネス Web アプリケーションまたは Skype 会議アプリケーションのエクスペリエンスの Skype のユーザーが、組織のネットワーク インフラストラクチャが構成されていない Office 365 のサポート[Office 365 の Url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)で説明するよう可能性があります。 Business Server のオンライン ビジネスや Skype の会議を Skype のユーザーによって作成されたかどうか、そうでは。 
  
ユーザーがネットワーク上に存在し、構成が記載どおりに行われていない場合、多くのアプリの機能が機能したりしなかったりする可能性があり、会議に接続することがまったくできない場合があります。
  
## <a name="supported-meetings-features"></a>サポートされる会議機能
<a name="BKMK_Conferencing"> </a>

この表では、Web アプリケーションのビジネス、Skype 会議アプリケーションでは、Lync Web App のビジネス クライアント用の Skype、Skype のユーザーに利用可能な会議の機能を比較します。 機能比較のための Lync Web App が表示されている: ユーザーのみをダウンロードし、会議が Lync 2013 のサーバーでホストされている場合は、Lync Web App を使用します。

| 機能 | Skype ビジネス 2016年または 2019年クライアント | Mac クライアントのビジネス用の Skype | Skype 会議アプリ | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|コンピューター オーディオの追加  <br/> |&#x2714;|&#x2714;|& #x 2714 です。(プラグインが必要です)  <br/> |& #x 2714 です。(プラグインが必要です)  <br/> |& #x 2714 です。(プラグインが必要です)  <br/> |
|ビデオの追加  <br/> |&#x2714;|&#x2714;|& #x 2714 です。(プラグインが必要です)  <br/> |& #x 2714 です。(プラグインが必要です)  <br/> |& #x 2714 です。(プラグインが必要です)  <br/> |
|オーディオを認証済み参加者の電話に切り替え  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|オーディオをゲスト参加者の電話に切り替え  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|マルチパーティのビデオの表示 (ギャラリー ビュー)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|ビデオベースの画面共有  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(View-only)  <br/> |||
|会議内発表者コントロールの使用  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|詳細な会議参加者一覧へのアクセス  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|マルチパーティ IM への参加  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|IM メッセージを「重要度 - 高」として設定  <br/> |&#x2714;|||||
|デスクトップの共有 (有効な場合)  <br/> |&#x2714;|&#x2714;|& #x 2714 です。(プラグインが必要です)  <br/> |& #x 2714 です。(プラグインが必要です)  <br/> |& #x 2714 です。(プラグインが必要です)  <br/> |
|プログラムの共有 (有効な場合)  <br/> |&#x2714;||& #x 2714; Windows でのみ使用できます。プラグインが必要です)  <br/> |& #x 2714; Windows でのみ使用できます。プラグインが必要です)  <br/> |& #x 2714; Windows でのみ使用できます。プラグインが必要です)  <br/> |
|他のユーザーの共有デスクトップまたはプログラムの制御します。  <br/> |&#x2714;||& #x 2714 です。(& #x 2776。[Windows の場合だけです。プラグインが必要です)  <br/> |& #x 2714 です。(& #x 2776。[Windows の場合だけです。プラグインが必要です)  <br/> |& #x 2714 です。(& #x 2776。[Windows の場合だけです。プラグインが必要です)  <br/> |
|別のユーザーによる共有デスクトップまたはプログラムの制御の許可  <br/> |&#x2714;|||||
|匿名参加者の追加 (有効な場合)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|名前で参加者を招待  <br/> |&#x2714;|&#x2714;||||
|電話番号で参加者を招待  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|メールで参加者を招待  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|ダイヤルイン音声会議の使用  <br/> |& #x 2714 です。& #x 2777 です。 |& #x 2714 です。& #x 2777 です。 |& #x 2714 です。& #x 2777 です。 |& #x 2714 です。& #x 2777 です。 |& #x 2714 です。& #x 2777 です。 |
|今すぐミーティングによる会議の開始  <br/> |&#x2714;|&#x2714;||||
|会議のレコーディング  <br/> |&#x2714;|||||
|添付ファイルの追加とダウンロード  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイルの追加と発表  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Microsoft PowerPoint ファイル内の移動  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|OneNote 会議ノートの追加と編集  <br/> |&#x2714;||編集のみ (追加不可)  <br/> |編集のみ (追加不可)  <br/> |編集のみ (追加不可)  <br/> |
|ホワイトボードの使用  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|投票の実行  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|他のユーザーと共有するファイルをアップロードする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|会議をスケジュールする  <br/> |Outlook または Skype のビジネス Web スケジューラ  <br/> |Outlook または Skype のビジネス Web スケジューラ  <br/> |ビジネス Web スケジューラの Skype  <br/> |ビジネス Web スケジューラの Skype  <br/> |ビジネス Web スケジューラの Skype  <br/> |
|Q&amp;マネージャー  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|出席者のビデオを無効にする  <br/> |&#x2714;|||||
|会議のインスタント メッセージを無効にする  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|参加者をミュートにする  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|全員を出席者にする  <br/> |&#x2714;|||||
|Skype 会議ブロードキャストを実施する  <br/> |&#x2714;|||||
   
 & #x 2776。 参加者には、Mac、Mac の 2011 年の Lync ユーザー Communicator for Mac 2011 のビジネス用の Skype によって共有されているデスクトップを制御できません。 不正解 Skype の Max OSX 上の Web アプリケーションのビジネス用です。
  
 & #x 2777 です。 オンライン ビジネスの Skype は、この機能は Exchange ユニファイド メッセージングと、Microsoft の PSTN 会議が必要ですまたはサードパーティのオーディオ会議プロバイダーです。
  
 & #x 2778 です。 2011 の Mac クライアント用の Lync では、それらと共有している会議で、Skype ビジネス Web アプリケーションの場合、Microsoft Office 2013 の PowerPoint プレゼンテーションを表示できません。
  
## <a name="known-issues-and-troubleshooting"></a>既知の問題とトラブルシューティング
<a name="BKMK_Conferencing"> </a>

エンド ・ ユーザーは、これらのアプリケーションの[オンライン ヘルプ](https://aka.ms/smahelp)はすぐに利用できます。 IT プロフェッショナルは、次の問題について認識する必要があります。
  
- ユーザーがネットワーク上に存在し、[ネットワーク要件](meetings-clients.md#Network)を満たすように構成されていない場合、多くのアプリの機能が機能したりしなかったりする可能性があり、会議に接続することがまったくできない場合があります。
    
- 一部のユーザーが、アプリをインストールするためのアクセス許可が無効化されている、会社管理のコンピューターを使用している場合があります。 、それらのユーザーのどちらもアプリケーションがオプションですが、[スマート フォン](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)や[タブレット](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)のユーザーは、ミーティングに参加するのには使用できる低コストのモバイル クライアントをインストールできる場合があります。
    
    その他のインストールに関する問題は、[ヘルプ トピック](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)にも説明します。 
    
- ユーザーが初めての警告ファイアウォールを参照してください、会議アプリケーションを実行します。 エクスペリエンスを最適化するためにポートを開く、メッセージが表示ことがあり、しない可能性がありますコンピューターに管理者特権が必要です。 アプリケーションがまだ機能する必要があり、ユーザーは要求されたポートを開くことを拒否できる安全にします。 
    
- [ActiveX を使用するフィルタ リング](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)の必要 Internet Explorer では、IE ではない場合でも、既定のブラウザーです。 ビジネス Web アプリケーションで、ActiveX コントロールの Skype で-小さなモジュールを web アプリケーションまたはその他のプログラムの追加機能を追加する-は、オーディオ、ビデオ、および画面共有に必要です。
    
- 正常に動作する Web アプリケーションのビジネス用の Skype のいくつかの機能では、コンピューターまたはデバイス上の[cookie を保存](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)するにはブラウザーを許可する必要があります。
    
- 可能性があります必要がある[JavaScript を有効に](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)するのにをサポートする正常に動作する Web アプリケーションのビジネス機能のいくつかの Skype には、ブラウザーで。
    
### <a name="aes-support"></a>AES のサポート 

ビジネス サーバー 2015 CU5 の Skype は、現在 ASP.NET 4.6 では、AES はサポートされていませんし、Skype の会議アプリケーション起動に失敗が発生する可能性があります。 [ASP .NET 4.5 のための暗号化の要件](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45)には、詳細情報があります。
  
## <a name="see-also"></a>関連項目
<a name="BKMK_Conferencing"> </a>

[Skype for Business Server で Web ダウンロード可能なクライアントを展開する](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会議アプリでサポートされるプラットフォーム](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
