---
title: サーバーのポートとプロトコルの要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: '概要: Skype for Business Server を実装する前に、ポートの使用に関する考慮事項を確認します。'
ms.openlocfilehash: 227fcbccf815886c5afa55c843ba59688f471a29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834307"
---
# <a name="port-and-protocol-requirements-for-servers"></a>サーバーのポートとプロトコルの要件
 
**概要:** Skype for Business Server を実装する前に、ポートの使用に関する考慮事項を確認します。
  
Skype for Business Server では、外部および内部ファイアウォール上の特定のポートを開いている必要があります。 さらに、組織でインターネット プロトコル セキュリティ (IPsec) が展開されている場合は、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートの範囲に対して IPsec を無効にする必要があります。 
  
これは最初は少し困難に思われるでしょうが、これを計画する作業は [Skype for Business Server 2015 計画ツールを使用して行う必要があります](https://go.microsoft.com/fwlink/p/?LinkID=282725)。 使用する予定の機能に関するウィザードの質問を確認したら、定義するサイトごとに、エッジ管理レポート内でファイアウォール レポートを表示し、ここに示す情報を使用してファイアウォール ルールを作成できます。 使用される名前と IP アドレスの多くを調整することもできます。詳細については、「ファイアウォール レポートの確認」 [を参照してください](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)。 エッジ管理レポートは Excel スプレッドシートにエクスポートできます。また、ファイアウォール レポートはファイル内のワークシートの 1 つになるので、ご安心ください。 
  
これらの表の情報は [、Skype for Business Server 2015](../../technical-diagrams.md) の技術ダイアグラムにリンクされている Protocol Workloads ポスターを参照して、図形式で確認することもできます。
> [!NOTE]
> - If you're implementing Skype for Business Online (Microsoft 365 or Office 365) refer to [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). ハイブリッド環境では、このトピックを参照し、ハイブリッド接続を [計画する必要があります](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
> - ハードウェアまたはソフトウェアのファイアウォールを使用できます。特定のモデルやバージョンは必要とされます。 重要なのは、ファイアウォールが Skype for Business Server の機能を損なわないポートをホワイトリストに追加する点です。
  
## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

このセクションでは、Skype for Business Server 展開のサーバー、ロード バランサー、およびクライアントで使用されるポートとプロトコルの概要を示します。
  
> [!NOTE]
> Skype for Business Server が起動すると、Windows ファイアウォールで必要なポートが開きます。 Windows ファイアウォールは、ほとんどの通常のアプリケーションで既に実行されている必要がありますが、使用されていない場合は、Skype for Business Server が機能しません。 
  
エッジ コンポーネントのファイアウォール構成の詳細については [、Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md)のエッジ サーバーのシナリオを参照してください。 
  
次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。 
  
**必要なサーバー ポート (サーバー役割別)**

|サーバーの役割|サービス名|ポート|プロトコル|Notes|
|:-----|:-----|:-----|:-----|:-----|
|すべてのサーバー  |SQL ブラウザー  |1434  |UDP  |SQLローカルにレプリケートされた中央管理ストア データベースのコピー用のブラウザー。  |
|フロント エンド サーバー  |Skype for Business Server Front-End サービス  |5060  |TCP  |リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。  |
|フロント エンド サーバー  |Skype for Business Server Front-End サービス  |5061  | TCP (TLS) |サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信にも使用されます。  |
| フロント エンド サーバー |Skype for Business Server Front-End サービス  |444  | HTTPS <br/> TCP  |フォーカス (会議の状態を管理する Skype for Business Server コンポーネント) と個々のサーバー間の HTTPS 通信に使用されます。  <br/> このポートは、存続可能ブランチ アプライアンスとフロント エンド サーバー間の TCP 通信にも使用されます。  |
|フロント エンド サーバー  |Skype for Business Server Front-End サービス  |135  |DCOM およびリモート プロシージャ コール (RPC)  |ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。  |
|フロント エンド サーバー  |Skype for Business Server IM 会議サービス  |5062  |TCP  |インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 会議サービス  |8057  |TCP (TLS)  |クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 会議互換性サービス  |8058  |TCP (TLS)  |Live Meeting クライアントおよび以前のバージョンの Skype for Business Server からの永続共有オブジェクト モデル (PSOM) 接続をリッスンするために使用されます。  |
|フロント エンド サーバー  |Skype for Business Server 音声ビデオ会議サービス  |5063  |TCP  |音声ビデオ会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server 音声ビデオ会議サービス  |57501-65535  |TCP/UDP  |ビデオ会議で使用するメディア ポート範囲。  |
|フロント エンド サーバー  |Skype for Business Server Web 互換性サービス  |80  |HTTP  |HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 互換性サービス  |443  |HTTPS  |フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 互換性サービス  |8080  |TCP と HTTP  |外部アクセス用の Web コンポーネントで使用されます。  |
|フロント エンド サーバー  |Web サーバー コンポーネント  |4443  |HTTPS  |自動検出サインインの HTTPS (リバース プロキシから) および HTTPS フロント エンドプール間通信。  |
|フロント エンド サーバー  |Web サーバー コンポーネント  |8060  |TCP (MTLS)  ||
|フロント エンド サーバー  |Web サーバー コンポーネント  |8061  |TCP (MTLS)  ||
|フロント エンド サーバー  |Mobility Services コンポーネント  |5086  |TCP (MTLS)  |Mobility Services 内部プロセスで使用される SIP ポート  |
|フロント エンド サーバー  |Mobility Services コンポーネント  |5087  |TCP (MTLS)  |Mobility Services 内部プロセスで使用される SIP ポート  |
|フロント エンド サーバー  |Mobility Services コンポーネント  |443  |HTTPS  ||
|フロント エンド サーバー  |Skype for Business Server 会議アテンダント サービス (ダイヤルイン会議)  |5064  |TCP  |ダイヤルイン会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server 会議アテンダント サービス (ダイヤルイン会議)  |5072  |TCP  |Attendant (ダイヤルイン会議) の SIP 要求を受信するために使用されます。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP  |フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5068  |TCP  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5081  |TCP  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5082  |TCP (TLS)  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server アプリケーション共有サービス  |5065  |TCP  |アプリケーション共有の SIP リッスン要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server アプリケーション共有サービス  |49152-65535  |TCP  |アプリケーション共有で使用するメディア ポート範囲。  |
|フロント エンド サーバー  |Skype for Business Server 会議アナウンス サービス  |5073  |TCP  |Skype for Business Server 会議アナウンス サービス (つまり、ダイヤルイン会議用) の SIP 要求を受信するために使用されます。  |
|フロント エンド サーバー  |Skype for Business Server コール パーク サービス  |5075  |TCP  |コール パーク アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server オーディオ テスト サービス  |5076  |TCP  |オーディオ テスト サービスの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |該当なし  |5066  |TCP  |発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。  |
|フロント エンド サーバー  |Skype for Business Server 応答グループ サービス  |5071  |TCP  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server 応答グループ サービス  |8404  |TCP (MTLS)  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server 帯域幅ポリシー サービス  |5080  |TCP  |音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。  |
|フロント エンド サーバー  |Skype for Business Server ファイル共有サーバーへのアクセス  |445   |SMB/TCP  | ファイル共有サーバーに格納されているアドレス帳、会議コンテンツ、その他のアイテムを取得するために使用されます。  |
|フロント エンド サーバー  |Skype for Business Server 帯域幅ポリシー サービス  |448  |TCP  |Skype for Business Server 帯域幅ポリシー サービスによる通話受付管理に使用されます。  |
|中央管理ストアが存在するフロントエンド サーバー  | Skype for Business Server マスター レプリケーター エージェント サービス |445  |TCP  |中央管理ストアから Skype for Business Server を実行しているサーバーに構成データをプッシュするために使用されます。  |
|すべてのサーバー  |SQL ブラウザー  |1434  |UDP  |SQL管理ストア データのローカル レプリケート コピー用のブラウザーをローカルの管理SQL Serverします。  |
|すべての内部サーバー  |各種  |49152-57500  |TCP/UDP  |すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 音声を終了するすべてのサーバーで使用されます。フロントエンド サーバー (Skype for Business Server 会議アテンダント サービス、Skype for Business Server 会議アナウンス サービス、Skype for Business Server 音声ビデオ会議サービス用)、および仲介サーバー。  |
|Office Web Apps サーバー  ||443  ||Skype for Business Server が Web Apps サーバーに接続Office使用します。  |
|ディレクター  |Skype for Business Server Front-End サービス  |5060  |TCP  |リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。  |
|ディレクター  |Skype for Business Server Front-End サービス  |444  |HTTPS  <br/> TCP  |フロントエンドとディレクターの間のサーバー間通信。 さらに、クライアント証明書を (フロント エンド サーバーに) 公開するか、クライアント証明書が既に公開されている場合は検証します。  |
|ディレクター  |Skype for Business Server Web 互換性サービス  |80  |TCP  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。  |
|ディレクター  |Skype for Business Server Web 互換性サービス  |443  |HTTPS  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|ディレクター  |Skype for Business Server Front-End サービス  |5061  |TCP  |サーバー間の内部通信とクライアント接続に使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP  |フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5068  |TCP  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP (MTLS)  |フロント エンド サーバーからの SIP 要求で使用。  |
|常設チャット フロントエンド サーバー  |常設チャット SIP  |5041  |TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |Persistent Chat Windows Communication Foundation (WCF)  |881  |TCP (TLS) および TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |常設チャット ファイル転送サービス  |443  |TCP (TLS)  ||
   
> [!NOTE]
> 一部のリモート通話制御シナリオでは、フロント エンド サーバーまたはディレクターと PBX 間の TCP 接続が必要です。 Skype for Business Server では TCP ポート 5060 が使用されなくなりましたが、リモート通話コントロールの展開時に信頼済みサーバー構成を作成し、RCC 回線サーバーの FQDN をフロント エンド サーバーまたはディレクターが PBX システムへの接続に使用する TCP ポートに関連付ける。 詳細については、Skype for Business Server 管理シェル のドキュメントの **CsTrustedApplicationComputer** コマンドレットを参照してください。
  
次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。
  
**ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー**

|ロード バランサー|ポート|プロトコル|
|:-----|:-----|:-----|
|フロント エンド サーバーのロード バランサー  |5061  |TCP (TLS)  |
|フロント エンド サーバーのロード バランサー  |444  |HTTPS  |
|フロント エンド サーバーのロード バランサー  |135  |DCOM およびリモート プロシージャ コール (RPC)  |
|フロント エンド サーバーのロード バランサー  |80  |HTTP  |
|フロント エンド サーバーのロード バランサー  |8080  |TCP - フロントエンド サーバーからのルート証明書のクライアントとデバイスの取得 - NTLM によって認証されたクライアントとデバイス  |
|フロント エンド サーバーのロード バランサー  |443  |HTTPS  |
|フロント エンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|フロント エンド サーバーのロード バランサー  |5072  |TCP  |
|フロント エンド サーバーのロード バランサー  |5073  |TCP  |
|フロント エンド サーバーのロード バランサー  |5075  |TCP  |
|フロント エンド サーバーのロード バランサー  |5076  |TCP  |
|フロント エンド サーバーのロード バランサー  |5071  |TCP  |
|フロント エンド サーバーのロード バランサー  |5080  |TCP  |
|フロント エンド サーバーのロード バランサー  |448  |TCP  |
|仲介サーバーロード バランサー  |5070  |TCP  |
|フロントエンド サーバー ロード バランサー (プールが仲介サーバーも実行する場合)  |5070  |TCP  |
|ディレクターのロード バランサー  |443  |HTTPS  |
|ディレクターのロード バランサー  |444  |HTTPS  |
|ディレクターのロード バランサー  |5061  |TCP  |
|ディレクターのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
   
DNS 負荷分散を使用するフロント エンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。 次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。
  
**DNS 負荷分散を使用する場合のハードウェア ロード バランサー**

|ロード バランサー|ポート|プロトコル|
|:-----|:-----|:-----|
|フロント エンド サーバーのロード バランサー  |80  |HTTP  |
|フロント エンド サーバーのロード バランサー  |443  |HTTPS  |
|フロント エンド サーバーのロード バランサー  |8080  |TCP - フロントエンド サーバーからのルート証明書のクライアントとデバイスの取得 - NTLM によって認証されたクライアントとデバイス  |
|フロント エンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|ディレクターのロード バランサー  |443  |HTTPS  |
|ディレクターのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |

**必要なクライアント ポート**

|コンポーネント|ポート|プロトコル|Notes|
|:-----|:-----|:-----|:-----|
|クライアント  |67/68  |DHCP  |レジストラー FQDN を検索するために Skype for Business Server によって使用されます (つまり、DNS SRV が失敗し、手動設定が構成されていない場合)。  |
|クライアント  |443  |TCP (TLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |443  |TCP (PSOM/TLS)  |Web 会議セッションへの外部ユーザー アクセスで使用。  |
|クライアント  |443  |TCP (STUN/MSTURN)  |音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用  |
|クライアント  |3478  |UDP (STUN/MSTURN)  |外部ユーザーが A/V セッションとメディア (UDP) にアクセスするために使用されます。  |
|クライアント  |5061  |TCP (MTLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |6891-6901  |TCP  |Skype for Business クライアントと以前のクライアントとの間のファイル転送に使用されます。  |
|クライアント  |1024-65535 \*  |TCP/UDP  |オーディオ ポート範囲 (少なくとも 20 個のポートが必要)  |
|クライアント  |1024-65535 \*  |TCP/UDP  |ビデオ ポート範囲 (少なくとも 20 個のポートが必要)  |
|クライアント  |1024-65535 \*  |TCP  |ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。  |
|クライアント  |1024-65535 \*  |TCP  |アプリケーション共有。  |
|Aastra 6721ip 共通領域電話  <br/> Aastra 6725ip 卓上電話  <br/> HP 4110 IP 電話 (共通領域電話)  <br/> HP 4120 IP 電話 (卓上電話)  <br/> Polycom CX500 IP 共通領域電話  <br/> Polycom CX600 IP 卓上電話  <br/> Polycom CX700 IP 卓上電話  <br/> Polycom CX3000 IP 会議電話  |67/68  |DHCP  |一覧に示されているデバイスで、Skype for Business Server 証明書、プロビジョニング FQDN、およびレジストラー FQDN を検索するために使用されます。  |
   
\* これらのメディアの種類の特定のポートを構成するには、CsConferencingConfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。
  
> [!NOTE]
> Skype for Business クライアントのセットアップ プログラムは、必要なオペレーティング システム ファイアウォール例外をクライアント コンピューターに自動的に作成します。 

> [!NOTE]
> 外部ユーザー アクセスに使用するポートは、クライアントが組織のファイアウォールを通過する必要があるすべてのシナリオ (たとえば、他の組織がホストする外部通信や会議) に必要です。 
  
## <a name="ipsec-exceptions"></a>IPsec 例外

インターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301- 4309 を参照) が展開されているエンタープライズ ネットワークでは、音声、ビデオ、パノラマ ビデオの配信に使用されるポートの範囲で IPsec を無効にする必要があります。 これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。
  
次の表に、推奨される IPsec 例外設定を示します。 
  
**推奨される IPSec 例外設定**

|ルール名|発信元 IP アドレス|送信先 IP アドレス|プロトコル|送信元ポート|宛先ポート|認証要件|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|内部音声ビデオ エッジ サーバー/受信  |任意  |内部音声ビデオ エッジ サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|外部音声ビデオ エッジ サーバー/受信  |任意  |外部音声ビデオ エッジ サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|内部音声ビデオ エッジ サーバー/送信  |内部音声ビデオ エッジ サーバー  |任意  |UDP &amp; TCP  |任意  |任意  |認証しない  |
|外部音声ビデオ エッジ サーバー/送信  |外部音声ビデオ エッジ サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|仲介サーバー/受信  |任意  |仲介  <br/> サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|仲介サーバー/送信  |仲介  <br/> サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|会議アテンダント/受信  |任意  |会議アテンダントを実行するフロントエンド サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|会議アテンダント/送信  |会議アテンダントを実行するフロントエンド サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|音声ビデオ会議サーバー/受信  |任意  |フロントエンド サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|音声ビデオ会議/送信  |フロントエンド サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|Exchange/受信  |任意  |Exchange ユニファイド メッセージング  |UDP および TCP  |任意  |任意  |認証しない  |
|アプリケーション共有サーバー/受信  |任意  |アプリケーション共有サーバー  |TCP  |任意  |任意  |認証しない  |
|アプリケーション共有サーバー/送信  |アプリケーション共有サーバー  |任意  |TCP  |任意  |任意  |認証しない  |
|Exchange/送信  |Exchange ユニファイド メッセージング  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|クライアント  |任意  |任意  |UDP  |指定メディア ポート範囲  |任意  |認証しない  |
