---
title: Skype for Business Server のモビリティの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Skype for Business Server の Mobility の実装を計画します。
ms.openlocfilehash: 6452154db1047cfe91a7c8ceaf6ee6c63b94ee6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810077"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Skype for Business Server のモビリティの計画
 
Skype for Business Server の Mobility の実装を計画します。
  
Skype for Business Server を使用すると、モバイル デバイスで Skype for Business Server の機能を提供するモビリティ機能を展開できます。 この記事では、モビリティ機能の詳細について説明し、展開の計画に役立ちます。
  
Skype for Business Server のモビリティ機能は、Skype for Business のモバイル クライアントと、2010 に戻る Lync クライアントをサポートできます。 展開後、ユーザーはサポートされている iOS、Android、Windows Phone モバイル デバイスを使用して Skype for Business Server 展開に接続し、エンタープライズ VoIP 機能など、いくつかの異なる機能を利用できます。 以下に部分的な一覧が含まれています。 [また、Skype for Business](clients-and-devices/desktop-feature-comparison.md) のデスクトップ クライアント機能の比較で詳しい情報を確認できます。
  
- メッセージの送受信
    
- プレゼンスの表示
    
- 連絡先を表示する
    
- クリックして会議に参加する
    
- [Call via work] (仕事から通話)
    
- 単一の番号の範囲
    
- ボイス メール
    
- 欠場した通話の通知
    
- ボイス オーバー IP (VoIP)
    
- 参加者のビデオ (H.264)
    
- 会議コンテンツの表示 (PowerPoint とデスクトップ/アプリケーション共有)
    
これはすべて、Unified Communications Web API (UCWA) を通じて実行されます。 UCWA は Lync Server 2013 で初めて導入され、引き続き Skype for Business Server で使用されています。 Lync 2010 クライアントと通信するための追加の機能があります。これは Mobility Service (MCX) です。 これらは無料のサービスであり、Lync Server 2010 および 2013 クライアント、および Skype for Business クライアントが Skype for Business Server 展開に正常にアクセスできます。
  
> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
これらの機能はすべて Mobility が実装された後で利用できるが、一部のデバイスでは動作が少し異なる場合がある点に注意することが重要です。 Skype for Business のモバイル クライアント機能の比較で、どのデバイスでどの機能が動作するのかを説明する Web サイト [が提供されています](clients-and-devices/mobile-feature-comparison.md)。 クライアントとデバイスの計画にも、デバイスと OS [に関する多くの情報があります](clients-and-devices/clients-and-devices.md)。
  
モビリティは自動検出機能を利用します。これにより、クライアントは、ユーザーが URL を入力する必要なしに Skype for Business Server Web サービスを自動的に検索できます (知る必要もなし)。 トラブルシューティングを行う必要がある場合は、URL の手動入力が引き続きサポートされます。
  
プッシュ通知は、Skype for Business アプリがバックグラウンドで実行されていない場合 (または、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイスの場合) にもサポートされます。 プッシュ通知は、デバイスまたはアプリが非アクティブなときに発生するイベントに関してモバイル デバイスに送信されます。 良い例として、電話がアクティブではないときに IM メッセージが表示されない場合があります。その結果、プッシュ通知が送信されます (これは、アプリがバックグラウンドで実行されている場合など、トーストまたは通知として表示されます)。 プッシュ通知を使用すると、ユーザーは IM や音声通話を見逃しません。
  
詳細については、以下のセクションを参照してください。
  
- [モビリティ コンポーネント](mobility.md#MobilityComponents)
    
- [サポートされるトポロジ](mobility.md#SupportedTopos)
    
- [技術的要件](mobility.md#TechRequirements)
    
- [モビリティのニーズの定義](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>モビリティ コンポーネント
<a name="MobilityComponents"> </a>

Mobility for Skype for Business Server を構成する 4 つのサービスがあります。
  
- **Unified Communications Web API (UCWA)**
    
    Skype for Business Server のモバイル クライアントおよび Web クライアントとのリアルタイム通信のためのサービスを提供します。 Skype for Business Server を展開すると、内部および外部の Web サービスに UCWA 仮想ディレクトリが作成されます。 UCWA が有効なクライアントからの呼び出しを受け入れる、この仮想ディレクトリ内の仮想コンポーネント。 クライアント アプリは、次の場合に、REST (Representational State Transfer) インターフェイスを介して通信します。
    
  - プレゼンス
    
  - contacts
    
  - インスタント メッセージング (IM)
    
  - VoIP
    
  - ビデオ会議
    
  - collaboration
    
    UCWA は P-GET ベースのチャネルを使用して、着信呼び出し、着信 IM、メッセージなどのイベントをクライアント アプリに送信します。
    
- **モビリティ サービス (MCX)**
    
    モバイル デバイスで、IM、プレゼンス、連絡先などの Skype for Business Server の機能をサポートします。 Mobility Service は、モバイル デバイスで Skype for Business Server の機能をサポートすることを目的とした各プール内のすべてのフロントエンド サーバーにインストールされます。 Skype for Business Server 2015 をインストールすると、フロント エンド サーバーの内部 Web サイトと外部 Web サイトの両方に新しい仮想ディレクトリ (Mcx) が作成されます。
    
    > [!NOTE]
    > 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
- **自動検出サービス**
    
    ユーザーの場所を識別し、モバイル デバイスや他の Skype for Business クライアントが、ネットワークの場所に関係なくリソース (Skype for Business Server Web サービスの内部 URL と外部 URL、Mcx URL、UCWA URL など) を検索できます。 自動検出では、ハードコードされたホスト名 (ネットワーク内のユーザーには lyncdiscoverinternal、ネットワーク外のユーザーの場合は lyncdiscover)、ユーザーの SIP ドメインが使用されます。 HTTP または HTTPS を使用するクライアント接続をサポートします。 
    
    自動検出サービスは、すべてのフロントエンド サーバーと、モバイル デバイスで Skype for Business Server の機能をサポートすることを目的とした各プールのすべてのディレクターにインストールされます。 サービスをインストールすると、フロント エンド サーバーとディレクターの内部 Web サイトと外部 Web サイトの両方に新しい仮想ディレクトリ (自動検出) が作成されます。
    
- **プッシュ通知サービス**
    
    Skype for Business Online データ センターにあるクラウドベースのサービス。 Skype for Business クライアントをバックグラウンドで実行しない電話では、新しいイベントが発生すると、見つからないイベント (プッシュ通知と呼ばれる) の通知が代わりにモバイル デバイスに送信されます。 Mobility Service は、通知をプッシュ通知サービス (MPNS) に送信し、その通知をモバイル デバイスに送信します。 その後、ユーザーはモバイル デバイスで通知に応答してアプリをアクティブ化できます。 この機能にはエッジ サーバーが必要です。
    
## <a name="supported-topologies"></a>サポートされるトポロジ
<a name="SupportedTopos"> </a>

トポロジ計画では、次の Skype for Business Server アプリケーションがサポートされています。
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
この機能は、Skype for Business Server エッジ サーバーまたは Lync Server 2013 エッジ サーバーで使用できる必要があります。
  
2 つのネットワーク インターフェイスを持つ仲介サーバーの役割と一緒に展開する場合、Mobility Service はフロント エンド サーバーでサポートされますが、これらのインターフェイスを構成するには適切な手順を実行する必要があります。 仲介サーバーとして通信する特定のインターフェイスと、フロントエンド サーバーとして通信するネットワーク IP インターフェイスに IP アドレスを割り当てる必要があります。 これを行うには、トポロジ ビルダーで、既定の [すべての構成済み IP アドレスを使用する] の選択を使用する代わりに、各サービスの正しい IP アドレス **を選択** します。
  
## <a name="technical-requirements"></a>技術的要件
<a name="TechRequirements"> </a>

モバイル ユーザーが遭遇する可能性があるさまざまなモバイル アプリケーション シナリオを計画することが重要です。 たとえば、3G ネットワーク経由で接続して仕事以外のモバイル アプリを使い始め、仕事に到達したら企業の Wi-Fi ネットワークに切り替える場合があります。 建物から出る際に 4G に切り替える場合があります。 計画すると、これらのネットワークの移行をサポートし、一貫したユーザー エクスペリエンスを保証できます。
  
### <a name="dns-configuration"></a>DNS の構成

Mobility Services Mcx と UCWA は同じ方法で DNS を使用します。 自動検出では、モバイル デバイスは DNS を使用してリソースを検索します。 DNS 参照中に、内部 DNS レコード (lyncdiscoverinternal.[内部ドメイン名])。 内部 DNS レコードを使用して接続できない場合は、2 番目の接続が試行されます。今回は外部 DNS レコード (lyncdiscover.[sipdomain])。 では、2 つがある理由は何でしょうか。 ネットワーク内部のモバイル デバイスは、内部自動検出 URL を使用できます。 外部モバイル デバイスは、外部自動検出 URL を使用します。 どちらの場合も、自動検出サービスは、Mobility Service (Mcx および UCWA) を含む、ユーザーのホーム プールのすべての Web サービス URL を返します。
  
外部自動検出要求は、Skype for Business Server 用に構成したリバース プロキシを経由する必要があります。 ただし、内部 Mobility Service URL と外部 Mobility Service URL の両方が外部 Web サービスの FQDN に関連付けられている。 したがって、モバイル デバイスがネットワークの内部か外部かにかかわらず、デバイスは常にリバース プロキシを介して Skype for Business Server Mobility Service に外部で接続します。
  
> [!NOTE]
> 先ほどお知らせした通り、すべての Mobility Service トラフィック (内部および外部) はリバース プロキシを通過します。 しかし、内部トラフィックがインターフェイスを経由して離れるときに問題が発生する場合があります。その後、同じインターフェイスを試して戻ってくる必要があります。 これは、スプーフィング (正式には TCP パケット スプーフィングと呼ばれる) セキュリティ ルールに違反する可能性があります。 ヘア ピン留めで **モビリティ機能** を使用できる必要があります。
  
> [!NOTE]
> これを行う準備ができている場合は、ファイアウォールとは別のリバース プロキシを使用する方法も選択できます (セキュリティ上の理由から、スプーフィング防止は常にファイアウォールに適用する必要があります)。 これにより、ファイアウォールの外部インターフェイスではなくリバース プロキシの外部インターフェイスでヘアピンが発生する可能性があります。 これにより、リバース プロキシのルールを緩め、モビリティ機能を利用しながら、ファイアウォールでスプーフィングを適切に検出できます。 
  
> [!NOTE]
> このルートを使用する場合は、可能であれば、DNS ホストまたは CNAME レコードを使用して、ヘアピン動作 (ファイアウォールではない) のリバース プロキシを定義してください。 
  
企業ネットワークの内部と外部のユーザーをサポートするために構成する必要があるものがあります。
  
内部および外部 Web FQDN のルールは次のとおりです。
  
- 自動検出用の新しい CNAME または A (IPv6 の場合はホスト、AAAA) DNS レコード。
    
- 新しいファイアウォール ルール (ネットワーク経由のプッシュ通知をサポートするWi-Fi場合)。
    
- 自動検出用の内部サーバー証明書とリバース プロキシ証明書のサブジェクトの代替名。
    
- フロントエンド サーバーハードウェア負荷分散構成により、ソース アフィニティが変更されます。
    
Mobility Service および自動検出サービスをサポートするために必要なトポロジ要件は次のとおりです。
  
- フロントエンド プールの内部 Web FQDN は、フロントエンド プールの外部 Web FQDN とは異なる必要があります。
    
- 内部 Web FQDN は、企業ネットワーク内にのみ解決し、企業ネットワーク内からアクセスできる必要があります。
    
- 外部 Web FQDN は、インターネットにのみ解決し、インターネットからアクセスできる必要があります。
    
- 企業ネットワーク内のユーザーの場合は、Mobility Service URL を外部 Web FQDN にアドレス指定する必要があります。 この要件は Mobility Service に適用され、この URL にのみ適用されます。
    
- 企業ネットワークの外部のユーザーの場合、要求はフロントエンド プールまたはディレクターの外部 Web FQDN に移動する必要があります。
    
自動検出をサポートする場合は、SIP ドメインごとに次の DNS レコードを作成する必要があります。
  
- 組織のネットワーク内から接続するモバイル ユーザーをサポートする内部 DNS レコード。
    
- インターネットから接続するモバイル ユーザーをサポートする外部 (パブリック) DNS レコード。
    
内部自動検出 URL は、内部ネットワークの外部からアドレス指定できません。 外部自動検出 URL は、ネットワーク内からアドレス指定できません。 ただし、外部 URL でこれができない場合は、内部 URL が常に最初に試みらたため、モバイル クライアントの機能に影響を与える可能性はおそらく高くはないと考えられます。
  
### <a name="port-and-firewall-requirements"></a>ポートとファイアウォールの要件

このほとんどについては、他のドキュメントで説明しましたが、特に Mobility の場合は、存続可能ブランチ アプライアンス (SBA) にホームを持つユーザーがいる場合は、エンタープライズ Wi-Fi ネットワークで次のポートを開く必要があります。
  
- UcwaSipExternalListeningPort には 5088 が必要です。
    
- UcwaSipPrimaryListeningPort には 5089 が必要です。
    
### <a name="certificate-requirements"></a>証明書の要件

Skype for Business モバイル クライアントの自動検出を使用している場合は、証明書の SAN (サブジェクトの代替名) リストを変更して、モバイル クライアントからのセキュリティで保護された接続をサポートする必要があります。 証明書が既にイン Place にある場合は、ここで説明する SAN エントリを使用して新しい証明書を要求して割り当てる必要があります。 これは、自動検出サービスを実行するフロントエンド サーバーとディレクター (環境内の場合) ごとに実行する必要があります。 また、リバース プロキシ証明書の SAN リストを変更し、組織内のすべての SIP ドメインに SAN エントリを追加することをお勧めします。
  
これは、内部 CA (証明機関) から新しい証明書を要求する場合は簡単なプロセスですが、パブリック証明書の方が複雑であり、新しいパブリック証明書に多くの SIP ドメインを追加するコストが高い場合は、言うまでもなく、再要求のコストが高くなります。そのような状況では、サポートされているが推奨されないアプローチ **があります**。 最初の自動検出サービス要求をポート 80 経由で行うリバース プロキシを構成できます。ポート 443 は HTTPS (既定の構成は 443) ではなく HTTP を使用します。 その受信要求は、フロント エンド プールまたはディレクターのポート 8080 にリダイレクトされます。 これにより、このトラフィックは要求に HTTPS を使用しないので、証明書を変更する必要がなされません。 ただし、これはお勧めしませんが、この方法はお勧めしません。
  
### <a name="windows-and-iis-requirements"></a>Windows と IIS の要件

Skype for Business Server 環境でサポートされている Windows Server バージョンが必要です。 その結果、モビリティのニーズに合った IIS 8 または IIS 8.5 も必要になります。 既定の設定を変更する必要がありますがASP.NET Mobility Service インストーラーによって自動的に変更されます。
  
### <a name="hlb-requirements"></a>HLB の要件

フロント エンド プール用の HLB を含む Skype for Business Server のトポロジ (複数のフロントエンド サーバーを含むトポロジ) を使用している場合は、Web サービス トラフィック用の外部 Web サービス仮想 IP (VIP) をソース用に構成する必要があります。 ソース アフィニティは、1 つのクライアントからの複数の接続が同じサーバーに送信され、セッション状態を維持するのに役立ちます。
  
内部 Wi-Fi ネットワーク経由でのみ Skype for Business モバイル クライアントをサポートする予定の場合は、外部 Web サービスの VIP に関する説明に従って、内部 Web サービスの VIP をソース用に構成する必要があります。 この場合は、HLB source_addr Web サービスの内部の VIP に対して、TCP (または TCP) アフィニティを使用する必要があります。
  
このすべてについて詳しくは、Skype for Business のドキュメントの [負荷分散の要件をご覧](network-requirements/load-balancing.md) ください。
  
### <a name="reverse-proxy-requirements"></a>リバース プロキシの要件

Skype for Business モバイル クライアントの自動検出をサポートするには、次のように現在の公開ルールを更新する必要があります。
  
- リバース プロキシ証明書の SAN リストを更新し、最初の自動検出サービス要求に HTTPS を使用する場合は、lyncdiscover の Web 公開ルールを更新する必要があります \<sipdomain\> 。 これは通常、フロント エンド プール上の外部 Web サービス URL の発行方法と組み合わされます。
    
- リバース プロキシ証明書の SAN リストを更新する必要を回避するために最初の自動検出サービス要求に HTTP を使用することを決定した場合 (これはお勧めしません)、ポート HTTP/TCP 80 用の新しい Web 公開ルールを作成する必要があります (まだ更新されていない場合)。 そのルールが存在する場合は、lyncdiscover を含む更新を行います。\<sipdomain\> エントリを指定します。
    
## <a name="defining-your-mobility-needs"></a>モビリティのニーズの定義
<a name="MobilityNeeds"> </a>

トポロジ、コンポーネント、および技術要件を確認しました。次に、モビリティの実装の観点から、組織が必要とする可能性があるものについて説明します。
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Skype for Business モバイル クライアントの自動検出を使用しますか?

自動検出を使用することを強く推奨します。 上の「技術要件」セクションで説明したように、新しい内部および外部 DNS レコードを作成する必要があります。 自動検出を使用すると、Skype for Business クライアントは、URL を手動で入力する必要なく、任意の場所から Skype for Business Server Web サービスを自動的に検索できます。
  
必要に応じて、手動設定を使用できます。 これらの URL は、ユーザーがモバイル デバイスに入力する必要があります。
  
- **https:// \<ExtPoolFQDN\> アクセス用の /Autodiscover/autodiscoverservice.svc/Root。**
    
- **https:// \<IntPoolFQDN\> アクセスのための /Autodiscover/autodiscoverservice.svc/Root。**
    
繰り返しになりますが、自動検出を使用することをお勧めします。 トラブルシューティングの目的で、手動設定が役立つ場合があります。
  
### <a name="are-you-going-to-support-push-notifications"></a>プッシュ通知をサポートしますか?

プッシュ通知は、この機能をサポートするモバイル アプリケーションで、アプリがアクティブではない間にイベントをユーザーに通知するために使用されます。 エッジ サーバーは、Skype for Business Online データセンターにあるクラウドベースの Skype for Business Server プッシュ通知サービスとのフェデレーション関係を持つ必要があります。 プッシュ通知を有効にするには、コマンドレットを実行する必要があります。
  
> [!NOTE]
> Lync Server 2010 クライアントをまだ使用しているユーザーが存在する場合は、エンタープライズ WiFi ネットワーク上で TCP ポート 5223 を開いて送信する必要があります。 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>すべてのユーザーがすべてのモビリティ機能にアクセスするか、代わりにこれらの機能にアクセスできるユーザーを指定するか。

すべてのユーザーが使用できる一部の機能と、既定で設定されているかどうかを示す表を用意しています。 完全な一覧については [、New-CsMobilityPolicy を確認してください](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
  
> [!NOTE]
> これらのすべての機能のスコープは、グローバル/サイト/ユーザーです。 
  
|**機能**|**パラメーター名**|**説明**|**既定の設定**|
|:-----|:-----|:-----|:-----|
|モビリティを有効にする  <br/> |EnableMobility  <br/> |Skype for Business モバイル クライアントがインストールされている特定のスコープ内のユーザーを制御します。 ポリシーが False に設定されている場合、ユーザーはクライアントでサインインできます。  <br/> |正  <br/> |
|外部音声  <br/> |EnableOutsideVoice  <br/> |ユーザーが [仕事から通話] を使用する機能を有効にし、ユーザーは自分の携帯電話番号ではなく、自分の電話番号を使用して通話を送受信できます。 False に設定されている場合、ユーザーは、仕事用の電話番号を使用するときに携帯電話で通話を行う、または受け取る事ができない。  <br/> |正  <br/> |
|IP オーディオとビデオを有効にする  <br/> |EnableIPAudioVideo  <br/> |既定に設定すると、ユーザーは VoIP を使用して、モバイル デバイスで電話またはビデオ通話を送受信できます。 False に設定されている場合、ユーザーはモバイル デバイスを使用してこれらの操作を実行できません。  <br/> |正  <br/> |
|IP オーディオに WiFi を要求する  <br/> |RequireWiFiForIPAudio  <br/> |クライアントが携帯データ ネットワークではなく、WiFi で VoIP を使用して通話を行う必要があるかどうかを定義します。 True に設定されている場合、ユーザーは WiFi 経由で接続されている場合にのみ VoIP 通話を送受信できます。  <br/> |False  <br/> |
|IP ビデオに WiFi を要求する  <br/> |RequireWiFiForIPVideo  <br/> |クライアントが携帯データ ネットワークではなく WiFi でビデオ通話を送受信する必要があるかどうかを定義します。 True に設定されている場合、ユーザーは WiFi 経由で接続されている場合にのみ VoIP 通話を送受信できます。  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>会議に対して有効になっていないユーザーエンタープライズ VoIPクリックして参加を使用して会議に参加できる必要がありますか?

モビリティ機能と [仕事から通話] にアクセスするには、ユーザーがモバイル デバイスでエンタープライズ VoIP。 ただし、有効になっていない場合でも、適切な音声ポリシーが割り当てられている場合にのみ、モバイル デバイス上のリンクをクリックして会議に参加できます。 以下のどちらかの方法で実行できます。
  
- 特定の音声ポリシーをこれらのユーザーに割り当てる、または
    
- グローバル ポリシーまたはサイト レベルのポリシーが存在し、そのポリシーに適用される必要があります。
    
どちらの方法でも、割り当てる音声ポリシーには、ユーザーがダイヤルアウトして会議に参加できる場所を定義する公衆交換電話網 (PSTN) 使用法レコードとルートが必要です。
  
> [!NOTE]
> クリックして参加を使用するモバイル ユーザーは、関連する PSTN 使用法レコードとボイス ルートと共に音声ポリシーを必要とします。これは、モバイル デバイス上のリンクをクリックすると、Skype for Business Server からの発信通話が結果になるためです。 
  

