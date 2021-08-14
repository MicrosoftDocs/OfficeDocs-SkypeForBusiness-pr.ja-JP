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
description: '概要: ポートを実装する前に、ポートの使用状況に関する考慮事項をSkype for Business Server。'
ms.openlocfilehash: d2e3cf07dbdf7471cd1e2f535d619e8bece74ecc0a9f9e16d416b7cba46548c1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352625"
---
# <a name="port-and-protocol-requirements-for-servers"></a>サーバーのポートとプロトコルの要件
 
**概要:** ポートを実装する前に、ポートの使用状況に関する考慮事項をSkype for Business Server。
  
Skype for Business Server、外部ファイアウォールと内部ファイアウォールの特定のポートが開いている必要があります。 さらに、組織でインターネット プロトコル セキュリティ (IPsec) が展開されている場合は、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートの範囲に対して IPsec を無効にする必要があります。 
  
これは少し気が重いように見えるかもしれないが、これを計画する重い持ち上げは[、2015](https://go.microsoft.com/fwlink/p/?LinkID=282725)年の計画ツールを使用Skype for Business Server実行できます。 使用する予定の機能に関するウィザードの質問を確認したら、定義するサイトごとに、エッジ管理レポート内のファイアウォール レポートを表示し、そこに記載されている情報を使用してファイアウォール ルールを作成できます。 使用される名前と IP アドレスの多くを調整することもできます。詳細については [、「Review the Firewall Report」を参照してください](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)。 エッジ管理レポートを別のスプレッドシートにエクスポートExcel、ファイアウォール レポートはファイル内のワークシートの 1 つになる場合に備えておきます。 
  
これらの表の情報は[、2015 年 2015](../../technical-diagrams.md)年の技術図の「プロトコル ワークロード」のポスターを参照して、Skype for Business Serverします。

> [!NOTE]
> - Skype for Business Online (Microsoft 365 または Office 365) を実装する場合は、「Microsoft 365 URL と IP アドレスOffice 365[を参照してください](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)。 ハイブリッド環境では、このトピックを参照し、ハイブリッド接続を [計画する必要があります](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2floc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
> - ハードウェアファイアウォールまたはソフトウェア ファイアウォールを使用できます。 特定のモデルやバージョンは不要です。 重要なのは、ファイアウォールが許可リストの機能を損なわないポートを許可リストに追加Skype for Business Server。
  
## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

このセクションでは、サーバー、ロード バランサー、およびクライアントが使用するポートとプロトコルを、Skype for Business Serverします。
  
> [!NOTE]
> 起動Skype for Business Server、ファイアウォールで必要なポートを開Windowsします。 Windowsファイアウォールは、ほとんどの通常のアプリケーションで既に実行されている必要がありますが、使用されていない場合は、Skype for Business Server機能しません。 
  
エッジ コンポーネントのファイアウォール構成の詳細については、「Edge Server シナリオ in [Skype for Business Server 2015」を参照](../../plan-your-deployment/edge-server-deployments/scenarios.md)してください。 
  
次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。 
  
**必要なサーバー ポート (サーバー役割別)**

|サーバーの役割|サービス名|ポート|プロトコル|備考|
|:-----|:-----|:-----|:-----|:-----|
|すべてのサーバー  |SQL ブラウザー  |1434  |UDP  |SQL中央管理ストア データベースのローカルレプリケート コピーのブラウザー。  |
|Front-End サーバー  |Skype for Business Server Front-End サービス  |5060  |TCP  |リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。  |
|フロント エンド サーバー  |Skype for Business Server Front-End サービス  |5061  | TCP (TLS) |サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信にも使用されます。  |
| フロント エンド サーバー |Skype for Business Server Front-End サービス  |444  | HTTPS <br/> TCP  |フォーカス (会議の状態を管理するSkype for Business Serverコンポーネント) と個々のサーバーとの間の HTTPS 通信に使用されます。  <br/> このポートは、存続可能ブランチ アプライアンスとフロントエンド サーバー間の TCP 通信にも使用されます。  |
|フロント エンド サーバー  |Skype for Business Server Front-End サービス  |135  |DCOM およびリモート プロシージャ コール (RPC)  |ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。  |
|フロント エンド サーバー  |Skype for Business ServerIM 会議サービス  |5062  |TCP  |インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business ServerWeb 会議サービス  |8057  |TCP (TLS)  |クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。  |
|フロント エンド サーバー  |Skype for Business ServerWeb 会議の互換性サービス  |8058  |TCP (TLS)  |Live Meeting クライアントからの永続的な共有オブジェクト モデル (PSOM) 接続と、以前のバージョンのセッションをリッスンSkype for Business Server。  |
|フロント エンド サーバー  |Skype for Business Server電話/ビデオ会議サービス  |5063  |TCP  |音声ビデオ会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server電話/ビデオ会議サービス  |57501-65535  |TCP/UDP  |ビデオ会議で使用するメディア ポート範囲。  |
|フロント エンド サーバー  |Skype for Business ServerWeb 互換サービス  |80  |HTTP  |HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロント エンド サーバー  |Skype for Business ServerWeb 互換サービス  |443  |HTTPS  |フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロント エンド サーバー  |Skype for Business ServerWeb 互換サービス  |8080  |TCP と HTTP  |外部アクセス用の Web コンポーネントで使用されます。  |
|フロント エンド サーバー  |Web サーバー コンポーネント  |4443  |HTTPS  |自動検出サインイン用の HTTPS (リバース プロキシから) と HTTPS フロントエンドのプール間通信。  |
|フロント エンド サーバー  |Web サーバー コンポーネント  |8060  |TCP (MTLS)  ||
|フロント エンド サーバー  |Web サーバー コンポーネント  |8061  |TCP (MTLS)  ||
|フロント エンド サーバー  |Mobility Services コンポーネント  |5086  |TCP (MTLS)  |Mobility Services の内部プロセスで使用される SIP ポート  |
|フロント エンド サーバー  |Mobility Services コンポーネント  |5087  |TCP (MTLS)  |Mobility Services の内部プロセスで使用される SIP ポート  |
|フロント エンド サーバー  |Mobility Services コンポーネント  |443  |HTTPS  ||
|フロント エンド サーバー  |Skype for Business Server 会議アテンダント サービス (ダイヤルイン会議)  |5064  |TCP  |ダイヤルイン会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server 会議アテンダント サービス (ダイヤルイン会議)  |5072  |TCP  |応答 (ダイヤルイン会議) の着信 SIP 要求に使用されます。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server仲介サービス  |5070  |TCP  |フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server仲介サービス  |5068  |TCP  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server仲介サービス  |5081  |TCP  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server仲介サービス  |5082  |TCP (TLS)  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|フロント エンド サーバー  |Skype for Business Serverアプリケーション共有サービス  |5065  |TCP  |アプリケーション共有の SIP リッスン要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Serverアプリケーション共有サービス  |49152-65535  |TCP  |アプリケーション共有で使用するメディア ポート範囲。  |
|フロント エンド サーバー  |Skype for Business Server 会議アナウンス サービス  |5073  |TCP  |(つまり、ダイヤルイン会議用) Skype for Business Server 会議アナウンスサービスの受信 SIP 要求に使用されます。  |
|フロント エンド サーバー  |Skype for Business Serverコール パーク サービス  |5075  |TCP  |コール パーク アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Serverオーディオ テスト サービス  |5076  |TCP  |オーディオ テスト サービスの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |該当なし  |5066  |TCP  |発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。  |
|フロント エンド サーバー  |Skype for Business Server応答グループ サービス  |5071  |TCP  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server応答グループ サービス  |8404  |TCP (MTLS)  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server帯域幅ポリシー サービス  |5080  |TCP  |音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。  |
|フロント エンド サーバー  |Skype for Business Serverファイル共有サーバーへのアクセス  |445   |SMB/TCP  | ファイル共有サーバーに保存されているアドレス帳、会議コンテンツ、その他のアイテムを取得するために使用します。  |
|フロント エンド サーバー  |Skype for Business Server帯域幅ポリシー サービス  |448  |TCP  |帯域幅ポリシー サービスによる通話受付Skype for Business Serverに使用されます。  |
|中央管理ストアが存在するフロントエンド サーバー  | Skype for Business Serverマスター レプリケーター エージェント サービス |445  |TCP  |サーバーの全体管理ストアからサーバーを実行しているサーバーに構成データをプッシュSkype for Business Server。  |
|すべてのサーバー  |SQL ブラウザー  |1434  |UDP  |SQLサーバーの全体管理ストア データのローカル レプリケート コピー用のブラウザー (ローカル SQL Server インスタンス内)  |
|すべての内部サーバー  |各種  |49152-57500  |TCP/UDP  |すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用されます。フロントエンド サーバー (Skype for Business Server 会議アテンダント サービス、Skype for Business Server 会議アナウンス サービス、Skype for Business Server オーディオ/ビデオ会議サービス用)、仲介サーバー。  |
|OfficeWeb Apps サーバー  ||443  ||Web Apps サーバー Skype for Business Server接続するためにOffice使用されます。  |
|ディレクター  |Skype for Business Server Front-End サービス  |5060  |TCP  |リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。  |
|ディレクター  |Skype for Business Server Front-End サービス  |444  |HTTPS  <br/> TCP  |フロントエンドとディレクターの間のサーバー間通信。 さらに、クライアント証明書は (フロントエンド サーバーに) 発行するか、クライアント証明書が既に発行済みである場合は検証します。  |
|ディレクター  |Skype for Business ServerWeb 互換サービス  |80  |TCP  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。  |
|ディレクター  |Skype for Business ServerWeb 互換サービス  |443  |HTTPS  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|ディレクター  |Skype for Business Server Front-End サービス  |5061  |TCP  |サーバー間の内部通信とクライアント接続に使用。  |
|仲介サーバー  |Skype for Business Server仲介サービス  |5070  |TCP  |フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。  |
|仲介サーバー  |Skype for Business Server仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server仲介サービス  |5068  |TCP  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server仲介サービス  |5070  |TCP (MTLS)  |フロント エンド サーバーからの SIP 要求で使用。  |
|常設チャット フロントエンド サーバー  |常設チャット SIP  |5041  |TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |常設チャット Windowsコミュニケーションファンデーション (WCF)  |881  |TCP (TLS) と TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |常設チャット ファイル転送サービス  |443  |TCP (TLS)  ||
   
> [!NOTE]
> 一部のリモート通話制御シナリオでは、フロント エンド サーバーまたはディレクターと PBX 間の TCP 接続が必要です。 Skype for Business Server は TCP ポート 5060 を使用しなくなりましたが、リモート呼び出し制御の展開中に信頼できるサーバー構成を作成し、RCC Line Server FQDN をフロントエンド サーバーまたはディレクターが PBX システムへの接続に使用する TCP ポートに関連付ける。 詳細については、「管理シェル」のドキュメントの **「CsTrustedApplicationComputer** コマンドレットSkype for Business Server参照してください。
  
次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。
  
**ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー**

|ロード バランサー|ポート|プロトコル|
|:-----|:-----|:-----|
|フロント エンド サーバーのロード バランサー  |5061  |TCP (TLS)  |
|フロント エンド サーバーのロード バランサー  |444  |HTTPS  |
|フロント エンド サーバーのロード バランサー  |135  |DCOM およびリモート プロシージャ コール (RPC)  |
|フロント エンド サーバーのロード バランサー  |80  |HTTP  |
|フロント エンド サーバーのロード バランサー  |8080  |TCP - フロント エンド サーバーからのルート証明書のクライアントとデバイスの取得 - NTLM によって認証されたクライアントとデバイス  |
|フロント エンド サーバーのロード バランサー  |443  |HTTPS  |
|フロント エンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|フロント エンド サーバーのロード バランサー  |5072  |TCP  |
|フロント エンド サーバーのロード バランサー  |5073  |TCP  |
|フロント エンド サーバーのロード バランサー  |5075  |TCP  |
|フロント エンド サーバーのロード バランサー  |5076  |TCP  |
|フロント エンド サーバーのロード バランサー  |5071  |TCP  |
|フロント エンド サーバーのロード バランサー  |5080  |TCP  |
|フロント エンド サーバーのロード バランサー  |448  |TCP  |
|仲介サーバーのロード バランサー  |5070  |TCP  |
|フロントエンド サーバーロード バランサー (プールが仲介サーバーも実行する場合)  |5070  |TCP  |
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
|フロント エンド サーバーのロード バランサー  |8080  |TCP - フロント エンド サーバーからのルート証明書のクライアントとデバイスの取得 - NTLM によって認証されたクライアントとデバイス  |
|フロント エンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|ディレクターのロード バランサー  |443  |HTTPS  |
|ディレクターのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |

**必要なクライアント ポート**

|コンポーネント|ポート|プロトコル|備考|
|:-----|:-----|:-----|:-----|
|クライアント  |67/68  |DHCP  |レジストラー FQDN をSkype for Business Serverするために使用されます (つまり、DNS SRV が失敗し、手動設定が構成されていない場合)。  |
|クライアント  |443  |TCP (TLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |443  |TCP (PSOM/TLS)  |Web 会議セッションへの外部ユーザー アクセスで使用。  |
|クライアント  |443  |TCP (STUN/MSTURN)  |音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用  |
|クライアント  |3478  |UDP (STUN/MSTURN)  |A/V セッションおよびメディア (UDP) への外部ユーザー アクセスに使用されます。  |
|クライアント  |5061  |TCP (MTLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |6891-6901  |TCP  |クライアントと以前のクライアントの間Skype for Business転送に使用されます。  |
|クライアント  |1024-65535 \*  |TCP/UDP  |オーディオ ポート範囲 (少なくとも 20 個のポートが必要)  |
|クライアント  |1024-65535 \*  |TCP/UDP  |ビデオ ポート範囲 (少なくとも 20 個のポートが必要)  |
|クライアント  |1024-65535 \*  |TCP  |ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。  |
|クライアント  |1024-65535 \*  |TCP  |アプリケーション共有。  |
|Aastra 6721ip 共通領域電話  <br/> Aastra 6725ip 卓上電話  <br/> HP 4110 IP 電話 (共通領域電話)  <br/> HP 4120 IP 電話 (卓上電話)  <br/> Polycom CX500 IP 共通領域電話  <br/> Polycom CX600 IP 卓上電話  <br/> Polycom CX700 IP 卓上電話  <br/> Polycom CX3000 IP 会議電話  |67/68  |DHCP  |リストされているデバイスで、証明書、プロビジョニング FQDN、Skype for Business Serverレジストラー FQDN を検索するために使用されます。  |
   
\* これらのメディアの種類の特定のポートを構成するには、CsConferencingConfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。
  
> [!NOTE]
> クライアントのセットアップ プログラムSkype for Business、クライアント コンピューターに必要なオペレーティング システムファイアウォールの例外が自動的に作成されます。 

> [!NOTE]
> 外部ユーザー アクセスに使用されるポートは、クライアントが組織のファイアウォールを通過する必要があるシナリオ (他の組織がホストする外部通信や会議など) に必要です。 
  
## <a name="ipsec-exceptions"></a>IPsec の例外

インターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301-4309 を参照) が展開されているエンタープライズ ネットワークでは、オーディオ、ビデオ、およびパノラマ ビデオの配信に使用されるポートの範囲で IPsec を無効にする必要があります。 これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。
  
次の表に、推奨される IPsec 例外設定を示します。 
  
**推奨される IPSec 例外設定**

|ルール名|発信元 IP アドレス|送信先 IP アドレス|プロトコル|送信元ポート|宛先ポート|認証要件|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|内部音声ビデオ エッジ サーバー/受信  |任意  |内部音声ビデオ エッジ サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|外部音声ビデオ エッジ サーバー/受信  |任意  |外部音声ビデオ エッジ サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|内部音声ビデオ エッジ サーバー/送信  |内部音声ビデオ エッジ サーバー  |任意  |UDP &amp; TCP  |任意  |任意  |認証しない  |
|外部音声ビデオ エッジ サーバー/送信  |外部音声ビデオ エッジ サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|仲介サーバー/受信  |任意  |仲介  <br/> Server(s)  |UDP および TCP  |任意  |任意  |認証しない  |
|仲介サーバー/送信  |仲介  <br/> Server(s)  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|会議アテンダント/受信  |任意  |会議アテンダントを実行するフロントエンド サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|会議アテンダント/送信  |会議アテンダントを実行するフロントエンド サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|音声ビデオ会議サーバー/受信  |任意  |フロントエンド サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|音声ビデオ会議/送信  |フロントエンド サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|Exchange/受信  |任意  |Exchange ユニファイド メッセージング  |UDP および TCP  |任意  |任意  |認証しない  |
|アプリケーション共有サーバー/受信  |任意  |アプリケーション共有サーバー  |TCP  |任意  |任意  |認証しない  |
|アプリケーション共有サーバー/送信  |アプリケーション共有サーバー  |任意  |TCP  |任意  |任意  |認証しない  |
|Exchange/送信  |Exchange ユニファイド メッセージング  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|クライアント  |任意  |任意  |UDP  |指定メディア ポート範囲  |任意  |認証しない  |