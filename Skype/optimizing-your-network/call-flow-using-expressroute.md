---
title: "ExpressRoute を使用したコール フロー"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
description: "この記事では、Skype for Business Online および ExpressRoute の核となるコール フローの原則について説明し、これらのサービスを正しく理解し計画できるよう詳細な例をいくつか示します。"
---

# ExpressRoute を使用したコール フロー

この記事では、Skype for Business Online および ExpressRoute の核となるコール フローの原則について説明し、これらのサービスを正しく理解し計画できるよう詳細な例をいくつか示します。
  
Skype for Business Online を Office 365、Skype for Business Server ハイブリッド、または Skype for Business Cloud Connector エディションの一部として展開している場合、Skype for Business Online サービスを効率的に計画、展開、操作、およびトラブルシューティングできるように、Skype for Business クライアントとサーバー間の通信とコール フローについて理解しておく必要があります。
  
## コール フローの概要

このドキュメントでは、コール フロー用データを送信できるネットワーク セグメントについて説明し、インターネットまたは ExpressRoute を通るトラフィックと比較して、どのトラフィックがネットワークに対してローカルのままになるかを理解できるようにします。どのトラフィックで ExpressRoute が使用されるかを知ることは、ExpressRoute を使用することで企業が得るメリットを評価したり、ExpressRoute の使用を決定した後で展開の検証とトラブルシューティングを行うための ExpressRoute 展開のガイダンスを理解したりするのに役立ちます。
  
ここで説明するコール フローは、管理されているさまざまな要素 (ファイアウォール ルール、NAT 構成、プロキシ、ルーター構成を含む) の影響を受ける可能性があります。このドキュメントでは、推奨される設定が適用されていることを前提としています。推奨される設定について以下に説明します。
  
- [Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Office 365 向け Azure ExpressRoute](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)
    
- [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/)
    
上記のドキュメントに記載の手順とは異なる手順でセットアップおよび構成を行った場合、コール フローはドキュメントのとおりにはならない場合があります。また、ネットワーク ルートが非対称で最適でない、あるいは転送プロコトルが最適でないなど、構成の問題が発生することがあります。ExpressRoute が関連する場合はいつでも、非対称のルーティングは重要な考慮事項となります。これは、ExpressRoute が Office 365 への 2 つ目のパスを導入するためです。すなわち、1 つの方向でインターネットを使用するルート、もう 1 つの方向で ExpressRoute を使用する別のルートが可能になります。これによって、ステートフル ファイアウォールをトラバースする場合に戻り方向のトラフィックがブロックされます。
  
## ネットワーク セグメントとトラフィック タイプ

### ネットワーク セグメント

コール フローについて説明する前に、Skype for Business Online で使用されるネットワーク セグメントとメディアのタイプの理解に役立ついくつかの用語を定義する必要があります。
  
以下のコール フローの図は、4 つの異なるネットワーク セグメントを示しています。それぞれがパフォーマンス特性が異なる、別々の組織 (内部ネットワーク、ネットワーク サービス プロバイダー、そのインターネット ピアリング パートナー、および Microsoft) によって管理されます。ネットワーク パフォーマンス ターゲットのガイドラインについては、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)」を参照してください。
  
これから説明する各ネットワーク セグメントは、以下のとおりです。
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **ネットワーク** これは、制御および管理するネットワーク全体の一部であるネットワーク セグメントです。これには、オフィス内の接続、有線または無線、オフィスビル間の接続、オンプレミス データセンターへの接続、インターネット プロバイダーまたは ExpressRoute パートナーへの接続がすべて含まれています。
  
通常、ネットワークのエッジには、1 つ以上の境界ネットワークと、組織のセキュリティ ポリシーを強化し、セットアップおよび構成した特定のネットワーク トラフィックのみを可能にする、ファイアウォールまたはプロキシが含まれています。このネットワークを管理しているため、ネットワークのパフォーマンスを直接制御していることになります。また、ネットワーク評価を完了し、ネットワークのサイト内のパフォーマンス、およびネットワークから Skype for Business Online へのパフォーマンスを検証することをお勧めします。パフォーマンス要件を確認するには、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)」を参照してください。
  
 **インターネット** これは、ネットワーク全体の中で、組織のネットワークの外部から Skype for Business Online に接続しているユーザーが使用するネットワーク セグメントで、ExpressRoute が構成されていない場合にすべての接続に使用されます。インターネットおよびそのすべての接続は組織の管理者または Microsoft によって管理されないため、パフォーマンスおよびルーティング パスを決めることはできず、これは全体のコール フローと品質に最も大きく影響します。
  
 **ExpressRoute** これは、ネットワーク全体の中で、Microsoft ネットワークへの専用のプライベート接続を可能にするネットワーク セグメントです。これは、Skype for Business Online リアルタイム通信など、ネットワーク速度およびパフォーマンスに依存するすべてのワークロードに対し、ネットワークを Microsoft ネットワーク (Office 365 データストア) に接続するための推奨オプションです。ExpressRoute 接続はネットワークと Microsoft ネットワーク間で行われ、[ExpressRoute 接続プロバイダー](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) を使用してプライベートな管理ネットワークを提供します。99.9% アップタイムと Quality of Service (QoS) のサポートによってネットワーク輻輳時のリアルタイム メディアのパフォーマンスを向上させることが可能です。
  
 **Microsoft ネットワーク** これは、ネットワーク全体の中で、Office 365 サービスをサポートするネットワーク セグメントです。これには、Office 365 用のオンライン サーバー間のすべての接続が含まれます。Microsoft ネットワーク バックボーンをトラバースし、地理的地域間で送信されるトラフィックが含まれる可能性があります。
  
### トラフィックのタイプ

Skype for Business Online のネットワーク トラフィックは、大きく 2 つのカテゴリに分類され、コール フローの別のパスとして表示されます。
  
 **リアルタイム メディア** は RTP (Real-time Transport Protocol) 内でカプセル化されたデータで、オーディオ、ビデオ、アプリケーション共有、およびファイル転送ワークロードをサポートします。一般的に、メディア トラフィックは待ち時間感度が高いため、このトラフィックが最短パスを通るようにし、UDP をトランスポート層プロトコルとして使用します。TCP を使用すると待ち時間が長くなるためです。
  
 **シグナリング** は、クライアントとサーバー間、あるいはその他のクライアント間の通信リンクです。アクティビティ (呼び出しが開始される場合など) を制御し、IM を配信するために使用されます。一部のクライアントでは HTTP ベースの REST インターフェイスが使用されますが、ほとんどのシグナルリング トラフィックでは SIP プロトコルが使用されます。使いやすくするために、このタイプのトラフィックで HTTP および HTTPS または TLS 接続経由で通過可能なさまざまなシグナリングを検討中です。このトラフィックは待ち時間感度は低いですが、エンドポイント間の待ち時間が数秒を超えた場合はサービス停止や呼び出しタイムアウトが発生することがあります。
  
トラフィックの宛先については、すべての Office 365 サービスの「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)」を参照してください。URL ごとに、トラフィックの部分が Office 365 向け ExpressRoute をトラバースするかどうかを示します。ExpressRoute が有効化されている場合にインターネットが一部のトラフィックに使用されていることを示す図については、「[Office 365 向け Azure ExpressRoute](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)」を参照してください。ExpressRoute 経由でルーティング可能としてリストされる URL がインターネット経由でもルーティング可能であることを理解することは重要です。つまり、一部のシナリオでは、インターネットまたは ExpressRoute が使用されるかどうかに関する決定は、クライアントの場所と、プロキシ サーバーおよびファイアウォールの構成に依存します。また、Office 365 と関連付けられているすべての URL が ExpressRoute を使用できるわけではないため、ExpressRoute を ExpressRoute パートナーから購入した場合でもインターネット接続は必要です。
  
インターネット経由でのみ送信可能なトラフィックには、Certificate Revocation Lists (CRL)、DNS ルックアップ、名前解決などの共通インターネット依存関係、Office 365 管理センター向けなどの共有 Office 365 サービスの URL、Skype 消費者との相互運用性用テレメトリーおよびフェデレーション、および Skype 会議ブロードキャスト用にストリームされるメディアなどの Skype for Business Online の一部の非リアルタイム通信機能が含まれます。意思決定に役立てるため、ネットワーク ルーティング計画時の考慮事項について、「[Office 365 向け ExpressRoute でのルーティング](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)」を参照してください。
  
## Skype for Business によるコール フローの原則

特定のコール フロー シナリオの詳細を説明する前に、Skype for Business のコール フローを理解するのに役立つ 6 つの一般原則があります。
  
1. Skype for Business 会議は、会議開催者の自宅がある場所と同じ地域でホストされます。開催者がオンライン ユーザーの場合は Office 365 クラウド、会議開催者がオンプレミス ユーザーの場合はオンプレミス データセンターでホストされます。
    
2. クライアントからホストされている会議に送信されるメディア トラフィックは常に会議がホストされているサーバーに送信されます。これは、管理するデータセンター内のオンプレミス サーバー、または Office 365 クラウド内のオンライン サーバーである場合があります。ただし、エッジ サーバーは常にオンライン会議用のメディア フローに使用されます。
    
3. ピアツーピア通話用メディア トラフィックは、使用可能な最短のルートを取ります。優先されるルートは、リモートピア (クライアント) にダイレクトされますが、ファイアウォール ブロックなどのためにルートが使用できない場合は、1 つ以上のエッジ サーバーがトラフィックを中継します。
    
4. シグナリング トラフィックは常に、ユーザーが自宅で使用する、オンラインまたはオンプレミスのサーバーに送信されます。フロント エンド サーバーに直接接続できない場合は、エッジ サーバーが使用されます。
    
5. オンラインでホストされる会議に参加しているユーザーは常にエッジ サーバー (クライアント ファイアウォール構成のために必要な場合は 2 つ) を使用します。
    
6. オンプレミスでホストされる会議に参加するユーザーは通常、オンプレミス展開を含む同じネットワーク内から接続する場合はエッジ サーバーを使用せず、ネットワーク外から接続する場合には 1 つまたは 2 つのエッジ サーバーを使用します。
    
選択されるメディア パスの詳細については、「[ICE - エッジ メディア接続](https://aka.ms/AVEdge)」を参照してください。このビデオは Lync Server 2013 に関するものですが、原則とプロトコルは Skype for Business にも適用されます。
  
## ExpressRoute を利用する Skype for Business コール フロー

4 つのネットワーク セグメントと、Skype for Business コール フローに関するいくつかの一般的なガイド原則について理解したら、ここではその情報を使用して、ExpressRoute ネットワーク セグメントをトラバースする Skype for Business トラフィックについて理解することができます。
  
一般的に、1 つのエンドポントがネットワーク内にあり、その他のエンドポイントが Office 365 データセンター内にある場合、ネットワーク トラフィックは ExpressRoute 接続をトラバースします。これには、クライアントとサーバー間のシグナリング トラフィック、電話会議中に使用されるメディア トラフィック、オンライン エッジ サーバーを使用するピアツーピア通話が含まれます。
  
両方のエンドポイントがインターネットで直接通信可能である場合、またはネットワーク内に配置されている場合、トラフィックは ExpressRoute 接続をトラバースしません。これには、ピアツーピア通話用のメディア、インターネットからオンプレミス展開へのトラフィック、またはインターネットと Office 365 エッジ サーバー間のトラフィックが含まれます。この例としては、ホテルからオンライン会議に参加するユーザーが挙げられます。
  
## 基本的な Skype for Business コール フロー

上記で説明されている Skype for Business コール フローに関する一般原則を適用できるように、この記事の次のセクションには参照としていくつかの図が含まれています。これは可能なコール フローすべての完全リストではありませんが、上記で詳述されている原則の適用に役立ちます。また、図のシナリオは、オンライン、ハイブリッド、Cloud Connector、そして特殊なケースである Skype 会議ブロードキャストを含む、共通の展開タイプを網羅しています。
  
> [!NOTE]
> Skype for Business によって使用されるトラフィックのサブセットは ExpressRoute 経由でルーティング可能ではなく、常にインターネット パスを取ります。影響を受ける可能性がある URL を判断するには、「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)」を参照してください。 
  
### 顧客ネットワーク内からの Office 365 ユーザー用ピアツーピア通話
<a name="bk_Figure2"> </a>

ピアツーピア通話の場合、メディア トラフィックは常にその宛先への最短ルートを取ります。ただし、シグナリング トラフィックは、オンライン ユーザーが自宅で使用する Office 365 データセンターに送信されます。両方のユーザーが同じ WAN 上で、クライアントが直接通信することを妨げるものは何もないため、メディアは両ユーザー間で直接やり取りします。シグナリング トラフィックは、両方のユーザーに対し組織のデータセンターごとに送信される ExpressRoute 接続をトラバースします。このシナリオでのコール フローを確認するには、以下を参照してください。
  
 **ピアツーピアのコール フロー**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### オンラインでホストされている会議に参加しているネットワーク上のオンライン ユーザー
<a name="bk_Figure3"> </a>

ピアツーピアの例ではメディア トラフィックは常にその宛先への最短ルートを取りますが、オンライン会議の場合、宛先は Office 365 クラウド内にあります。つまり、ネットワーク内から会議に参加しているすべてのユーザーのメディア トラフィックは ExpressRoute 接続をトラバースし、シグナリング トラフィックは Office 365 クラウドに送信されます。以下の図は、メディアおよびシグナリングの両方がネットワーク内のユーザーの ExpressRoute 接続をトラバースし、コーヒー ショップやホテルなどのネットワーク外からインターネットに接続しているユーザーのインターネットを直接トラバースすることを示しています。
  
会議の場所は出席者ではなく、会議開催者によって定義されます。つまり、会議がオンプレミス顧客によってスケジュールされた場合、メディア トラフィックは ExpressRoute 経由で Office 365 クラウドに向かうのではなく、インターネットをトラバースして会議開催者のオンプレミス データセンターに向かいます。
  
オンライン会議用メディアの宛先はOffice 365 クラウド内のデータセンターとなりますが、データセンターは会議に参加しているユーザーとは異なる地理的領域にある可能性があります。これは、次のいずれかの場合に発生する可能性があります。
  
- 会議開催者が出席者または参加者とは異なる会社の従業員であり、開催者の組織が別の地理的場所または国/地域でホストされている場合。
    
- ユーザーがその会社の組織がある国/地域とは異なる国/地域から参加している場合 (会社が多国籍企業である、またはユーザーが出張中であるなど)。
    
このシナリオでの ExpressRoute を使用する利点は、ExpressRoute Premium アドオンによって、会議組織のデータセンターの開催者の地理的領域に関係なく、ExpressRoute パスをたどるデータが Microsoft のバックボーンを自動的に通過することです。
  
 **オンライン ユーザーとオンライン会議コール フロー**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### ハイブリッド展開のオンプレミス ユーザーによってホストされる会議の参加
<a name="bk_Figure3"> </a>

ホストされている会議をサポートする会議サーバーは、会議開催者の自宅がある場所によって決定されます。このシナリオでは、ハイブリッド展開のオンプレミス ユーザーによってスケジュールされた会議に参加しているすべてのユーザーのメディアは、オンプレミス データセンターに向かいます。オンライン自宅ユーザーのシグナリングは、Office 365 クラウドの組織を経由して確立され、メディアは直接接続を試行します。このシナリオでは両方のユーザーがネットワーク内から接続し、直接メディア通信が可能なため、ExpressRoute はオンライン自宅ユーザー用のシグナリング トラフィックにのみ使用されます。オンライン自宅ユーザーがインターネットから接続する場合、接続にオンライン エッジ サーバーが使用される場合はメディアは ExpressRoute をトラバースできます。
  
 **ハイブリッド ユーザー コール フローによってホストされる会議**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### オンプレミス エッジ サーバーと Office 365 ホスト会議
<a name="bk_Figure5"> </a>

ハイブリッド ユーザーがオンライン ホスト会議に参加する場合、シグナリングおよびメディアの宛先は Office 365 クラウドとなり、ユーザーがインターネットから参加しているため、通常は直接インターネット パスが取られます。ただし、場合によっては、ファイアウォール制限などのために直接インターネット パスが使用できないことがあります。この場合、オンプレミス エッジ サーバーはメディア トラフィックを中継し、これによりメディア トラフィックは ExpressRoute 回路をトラバースして Office 365 クラウドに向かう前にオンプレミス ネットワークに戻ります。
  
 **オンプレミス エッジ サーバーを使用してオンライン会議に参加しているオンプレミス ユーザー**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### Skype for Business Cloud Connector エディションを使用した PSTN 通話
<a name="bk_Figure6"> </a>

[Skype for Business Online Cloud Connector エディション](https://aka.ms/CloudConnectorInstaller) を使用すると、SIP トランク、PSTN ゲートウェイなどのオンプレミス リソース、または Skype for Business と統合するための最小ハードウェア デバイスを使用した PSTN 接続が提供されます。Cloud Connector エディションを使用して、ユーザーは自宅オンラインとなり、通話プランを利用しない場合は通常のオンライン ユーザーとなります。PSTN シナリオのシグナリングは利用できる場合は ExpressRoute 接続でクライアントとクラウド間を通過し、メディア トラフィックは WAN 内にとどまります。この場合、シグナリングは Office 365 クラウドで方向転換し、Cloud Connector で終了します。
  
 **Office 365 および Cloud Connector の電話システムによる PSTN 通話**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### ユーザーが顧客ネットワークから参加している Skype 会議ブロードキャスト
<a name="bk_Figure6"> </a>

Skype 会議ブロードキャストは特殊な使用事例です。2 つのパートの会議から構成され、各パートには異なるネットワーク転送プロファイルが含まれています。ネットワーク パフォーマンスの観点から最も重要な最初のパートは、内部会議です。これは会議のリアルタイム部分です。Office 365 クラウドの会議サーバーに接続する 1 つ以上のクライアント エンドポイントが含まれます。会議のこの部分を使用して送信されるデータは、ちょうど上記の例のようになり、Office 365 ユーザーが参加する、オンライン会議となります。
  
Skype 会議ブロードキャストが独特である理由は、会議がブロードキャスト ストリーミング サービスを使用して多くの会議出席者に配信されるためです。このブロードキャスト ストリーミング サービスは ExpressRoute 経由ではティングできませんが、代わりに Content Delivery Network (CDN) サービスをオプションでサポートするインターネットが使用されます。ブロードキャスト ストリーミングが一方向のメディア フローであることを認識することは有用です。出席者は相手の話を聴きますが、自分では話さず、バッファリングをサポートするため、待ち時間、パケット損失、ジッターなどのネットワーク パフォーマンスの問題に敏感でないためです。こうした問題に対しブロードキャスト トラフィックを最適化する代わりに、非常に多くの出席者がストリーム メディアを受信しているため、バンド幅利用に向けて最適化されます。
  
 **ユーザーが顧客ネットワークから参加している Skype 会議ブロードキャスト**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## 展開タイプ別のコール フロー パターン

上記に示した共通のコール フローの例と、トラフィック パターンを制御する一般原則に関する理解を基に、以下の表に展開と使用シナリオの大規模な組み合わせに対するトラフィック パターンの概要を示します。これらの表にはコール フローの可能な組み合わせがすべて網羅されているわけではありませんが、コール フローの一般原則について理解するために役立つはずです。
  
データは送信され、組織のローカルとしてリストされ、顧客ネットワーク、インターネット、または ExpressRoute を離れることはありません。上記にリストされているパターンは、ファイアウォール、フェデレーション、インターネットなどの最も一般的なネットワーク設定に基づいており、マルチパーティまたはフェデレーション フローに関連するすべての組織に ExpressRoute があることを想定します。実際には、設定が異なると、トラフィック パターンは以下にリストされるものと異なります。
  
### Skype for Business Online のコール フロー

Skype for Business Online 使用シナリオでは、自宅オンラインのユーザーが関連し、内部ネットワークまたはインターネットから電話をかけている可能性があります。オンプレミス サーバーはこれらのシナリオの一部ではありません。そのため、すべての会議または PSTN 関連のメディアは Office 365 クラウドに向かい、オンライン ユーザーのエッジ サーバーもそのクラウド内にあることになります。
  
 **Skype for Business Online のコール フローの概要**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用シナリオ** <br/> |**エンドポイント** <br/> |**シグナリング パス** <br/> |**メディア パス** <br/> |**サンプル フロー** <br/> |**メモ** <br/> |
|ピアツーピア通話  <br/> |2 つのクライアント、両方ともにネットワーク上。  <br/> |ExpressRoute  <br/> |ローカル  <br/> |[顧客ネットワーク内からの Office 365 ユーザー用ピアツーピア通話](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|ピアツーピア通話  <br/> |2 つのクライアント、1 つはネットワーク上 (内部)、もう 1 つはインターネット上 (外部)。  <br/> |内部ユーザー: ExpressRoute  <br/> 外部ユーザー: インターネット  <br/> |内部ユーザー: ExpressRoute  <br/> 外部ユーザー: インターネットから Office 365 Edge サーバーへ。  <br/> |[顧客ネットワーク内からの Office 365 ユーザー用ピアツーピア通話](call-flow-using-expressroute.md#bk_Figure2) <br/> |ファイアウォールがクライアント間の直接接続をブロックするとします。これにはオンライン エッジ サーバーが必要です。内部ユーザーからオンライン エッジ サーバーへのトラフィックは、電話会議用の会議サーバーへのパスと似たパスをたどります。  <br/> |
|フェデレーション関係にある組織のユーザーへのピアツーピア通話  <br/> |2 つのクライアント、1 つはネットワーク上 (内部)、もう 1 つはフェデレーション関係にある組織のネットワーク上のオンライン ユーザー (フェデレーション)  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[オンラインでホストされている会議に参加しているネットワーク上のオンライン ユーザー](call-flow-using-expressroute.md#bk_Figure3) <br/> |ファイアウォールがクライアント間の直接接続をブロックし、オンライン エッジ サーバーが必要であるとします。内部ユーザーからオンライン エッジ サーバーへのトラフィックは、電話会議用の会議サーバーのパスと似たパスをたどります。  <br/> |
|顧客ネットワークのユーザーによる電話会議の参加  <br/> |ネットワーク上および Office 365 クラウドの会議サーバー上のクライアント  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[オンラインでホストされている会議に参加しているネットワーク上のオンライン ユーザー](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|インターネットのユーザーによる電話会議への参加  <br/> |クライアントはインターネット上および Office 365 クラウドの会議サーバー上です。  <br/> |インターネット  <br/> |インターネット  <br/> |[オンラインでホストされている会議に参加しているネットワーク上のオンライン ユーザー](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|別の会社のオンプレミス サーバーによってホストされる会議の参加  <br/> |ネットワーク上およびサードパーティー データセンターの会議サーバー上のクライアント。  <br/> |インターネット  <br/> |インターネット  <br/> |該当しない  <br/> |会議をホストする会議サーバーが異なる顧客オンプレミス ネットワーク上にあるため、データは Microsoft クラウドを通過しません。  <br/> |
|PSTN 通話  <br/> |顧客ネットワーク上および Office 365 クラウドの電話システムサーバー上のクライアント  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[オンラインでホストされている会議に参加しているネットワーク上のオンライン ユーザー](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 通話  <br/> |インターネット上および Office 365 クラウドの電話システムサーバー上のクライアント  <br/> |インターネット  <br/> |インターネット  <br/> |該当しない  <br/> |メディアおよびシグナリングは Office 365 データセンターに流れます。クライアント エンドポイントがインターネット上にあるため、すべてのデータはインターネットで Microsoft データセンターに向かいます (オンライン エッジ サーバーが接続に必要な場合でも)。  <br/> |
   
> [!NOTE]
> ExpressRoute は、会社のネットワークに配置されているユーザーからオンライン エッジ サーバーへのメディア パスで使用され、別の顧客のオンプレミス配置用エッジ サーバーが使用される場合は使用されません。 
  
### Skype for Business ハイブリッドのコール フロー

ハイブリッドのコール フローは、自宅オンプレミスの少なくとも一部のユーザーが含まれる Skype for Business 展開があるときに適用されます。このセクションのコール フローには、両方のオンプレミス会議、および少なくとも 1 人のオンプレミス自宅ユーザーを含むピアツーピアまたは PSTN 通話が含まれます。
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用シナリオ** <br/> |**エンドポイント** <br/> |**シグナリング パス** <br/> |**メディア パス** <br/> |**サンプル フロー** <br/> |**メモ** <br/> |
|ピアツーピア通話  <br/> |2 つのクライアント、顧客ネットワーク上および自宅オンプレミス上  <br/> |ローカル  <br/> |ローカル  <br/> |[顧客ネットワーク内からの Office 365 ユーザー用ピアツーピア通話](call-flow-using-expressroute.md#bk_Figure2) <br/> |ユーザーは自宅オンプレミスであるため、シグナリングは Office 365 クラウドではなく、ローカルにオンプレミス データセンターに向かいます。  <br/> |
|ピアツーピア通話  <br/> |2 つのクライアント、両方が顧客ネットワークから接続 1 つは自宅オンライン、もう 1 つは自宅オンプレミス  <br/> |オンライン ユーザー: ExpressRoute  <br/> オンプレミス ユーザー: ローカル  <br/> |ローカル  <br/> |[顧客ネットワーク内からの Office 365 ユーザー用ピアツーピア通話](call-flow-using-expressroute.md#bk_Figure2) <br/> |オンライン自宅ユーザーのみがシグナリング トラフィックを Office 365 クラウドに送信します。  <br/> |
|フェデレーション関係にある組織のユーザーへのピアツーピア通話  <br/> |2 つのクライアント、1 つは顧客ネットワークのオンプレミス ユーザー (内部)、もう 1 つはフェデレーション関係にある会社のネットワークのオンライン ユーザー (フェデレーション)  <br/> |内部ユーザー: ローカル  <br/> フェデレーション関係にあるユーザー１：ExpressRoute  <br/> |インターネットまたは ExpressRoute (オンラインまたはオンプレミス エッジ サーバーが使用されているかどうかに依存)  <br/> |[オンラインでホストされている会議に参加しているネットワーク上のオンライン ユーザー](call-flow-using-expressroute.md#bk_Figure3)と[オンプレミス エッジ サーバーと Office 365 ホスト会議](call-flow-using-expressroute.md#bk_Figure5) の一部 (メディア トラフィックの場合) <br/> |ファイアウォールがクライアント間の直接接続をブロックしていて、オンライン エッジ サーバーが必要であるとします。ICE ネゴシエーションにより接続に対してオンライン (オンライン ユーザーによる) およびオンプレミス エッジサーバ (オンプレミス ユーザーによる) が提供されます。  <br/> |
|顧客ネットワークのユーザーによる会議の参加 (オンライン ユーザーによってスケジュールされた会議)  <br/> |ネットワーク上および Office 365 クラウドの会議サーバー上のオンプレミス ユーザー  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[オンラインでホストされている会議に参加しているネットワーク上のオンライン ユーザー](call-flow-using-expressroute.md#bk_Figure3) <br/> |電話会議のサーバー リソースは、会議開催者によって定義されます。この場合、オンライン ユーザーによってスケジュールされたため、リソースは Office 365 クラウド内です。  <br/> |
|PSTN 通話  <br/> |ネットワーク上およびオンプレミス Skype for Business データセンター上のオンプレミス ユーザー。  <br/> |ローカル  <br/> |ローカル  <br/> |[Skype for Business Cloud Connector エディションを使用した PSTN 通話](call-flow-using-expressroute.md#bk_Figure6) <br/> |Cloud Connector エディションの使用に似たシナリオ。ユーザーが自宅オンプレミスの場合を除くため、シグナリングはネットワーク内にとどまります。  <br/> |
   
### Cloud Connector による Skype for Business のコール フロー

Cloud Connector に接続するユーザーはすべて自宅オンラインです。つまり、会議はオンラインとなり、シグナリングはオンライン ユーザーと同じパターンをたどります。PSTN 通話以外のシナリオの場合、コール フローは Skype for Business Online について上記で説明されているとおりです。
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用シナリオ** <br/> |**エンドポイント** <br/> |**シグナリング パス** <br/> |**メディア パス** <br/> |**サンプル フロー** <br/> |**メモ** <br/> |
|PSTN 通話  <br/> |Cloud Connector エディションを使用したネットワーク上のオンライン ユーザー。  <br/> |ローカル  <br/> |ローカル  <br/> |[Skype for Business Cloud Connector エディションを使用した PSTN 通話](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN 通話  <br/> |Cloud Connector エディションを使用したインターネットを使用したオンライン ユーザー。  <br/> |インターネット  <br/> |インターネット  <br/> |[オンプレミス エッジ サーバーと Office 365 ホスト会議](call-flow-using-expressroute.md#bk_Figure5) と[Skype for Business Cloud Connector エディションを使用した PSTN 通話](call-flow-using-expressroute.md#bk_Figure6) の組み合わせ。 <br/> |インターネット ユーザーは Cloud Connector に含まれているエッジサーバー経由で接続し、Cloud Connector は PSTN ネットワークに接続します。  <br/> |
   
