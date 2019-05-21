---
title: サーバーのポートとプロトコルの要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: '概要: Skype for Business Server を実装する前に、ポートの使用に関する考慮事項を確認します。'
ms.openlocfilehash: 613067d90da4fb06811ca1497c83237019b3c021
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297023"
---
# <a name="port-and-protocol-requirements-for-servers"></a>サーバーのポートとプロトコルの要件
 
**概要:** Skype for Business Server を実装する前に、ポートの使用に関する考慮事項を確認します。
  
Skype for Business Server を使用するには、外部および内部のファイアウォールの特定のポートを開く必要があります。 さらに、組織でインターネット プロトコル セキュリティ (IPsec) が展開されている場合は、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートの範囲に対して IPsec を無効にする必要があります。 
  
これは少し困難に思えるかもしれませんが、計画を立てるための大きな取り組みは、 [Skype For Business Server 2015 計画ツール](https://go.microsoft.com/fwlink/p/?LinkID=282725)を使って行うことができます。 使用する予定の機能についてウィザードの質問がある場合は、定義した各サイトについて、エッジ管理者レポートでファイアウォールレポートを表示して、そこに記載されている情報を使って、ファイアウォールルールを作成することができます。 使用する名前と IP アドレスの多くを調整することもできます。詳細については、「[ファイアウォールレポートを確認](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)する」を参照してください。 Edge 管理レポートを Excel スプレッドシートにエクスポートして、ファイアウォールレポートをファイル内のワークシートの1つとしてエクスポートすることはできますので注意してください。 
  
また、 [Skype For Business Server 2015 に関するテクニカルダイアグラム](../../technical-diagrams.md)からリンクされたプロトコルワークロードのポスターを参照して、これらの表の情報をダイアグラム形式で見つけることもできます。
> [!NOTE]
> - Skype for Business Online (O365) を実装している場合は、「 [Office 365 の url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」を参照してください。 ハイブリッド環境では、このトピックを参照し、[ハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)する必要があります。
> - ハードウェアまたはソフトウェアのファイアウォールを使用できますが、特定のモデルやバージョンは必要ありません。 重要なのは、どのポートがホワイトリストに含まれており、ファイアウォールによって Skype for Business Server の機能が損なわれないためです。
  
## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

このセクションでは、Skype for Business Server 展開のサーバー、ロードバランサー、クライアントで使用されるポートとプロトコルについて概要を説明します。
  
> [!NOTE]
> Skype for Business Server が起動すると、Windows ファイアウォールの必要なポートが開きます。 Windows ファイアウォールは、ほとんどの通常のアプリケーションで既に実行されていますが、使用されていない場合は、Skype for Business Server は動作しなくなります。 
  
エッジコンポーネントのファイアウォール構成の詳細については、「 [Skype For Business server 2015 のエッジサーバーのシナリオ](../../plan-your-deployment/edge-server-deployments/scenarios.md)」を参照してください。 
  
次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。 
  
**必要なサーバー ポート (サーバー役割別)**

|サーバーの役割|サービス名|ポート|プロトコル|メモ|
|:-----|:-----|:-----|:-----|:-----|
|すべてのサーバー  |SQL ブラウザー  |1434  |UDP  |中央管理ストアデータベースのローカルでレプリケートされたコピーの SQL ブラウザー。  |
|フロントエンド サーバー  |Skype for Business Server のフロントエンドサービス  |5060  |TCP  |リモート通話コントロール サーバーなどの Standard Edition サーバーとフロントエンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。  |
|フロントエンド サーバー  |Skype for Business Server のフロントエンドサービス  |5061  | TCP (TLS) |サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロントエンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロントエンド プールで使用。監視サーバーとの通信でも使用。  |
| フロントエンド サーバー |Skype for Business Server のフロントエンドサービス  |444  | HTTPS <br/> TCP  |フォーカス (会議の状態を管理する Skype for Business Server コンポーネント) と個々のサーバーの間の HTTPS 通信に使用されます。  <br/> このポートは、Survivable Branch アプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。  |
|フロントエンド サーバー  |Skype for Business Server のフロントエンドサービス  |135  |DCOM およびリモート プロシージャ コール (RPC)  |ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。  |
|フロントエンド サーバー  |Skype for Business Server IM 会議サービス  |5062  |TCP  |インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server Web 会議サービス  |8057  |TCP (TLS)  |クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。  |
|フロントエンド サーバー  |Skype for Business Server Web 会議の互換性サービス  |8058  |TCP (TLS)  |Live Meeting クライアントと以前のバージョンの Skype for Business Server からの永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。  |
|フロントエンド サーバー  |Skype for Business Server の音声/ビデオ会議サービス  |5063  |TCP  |音声ビデオ会議の SIP 要求を受信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server の音声/ビデオ会議サービス  |57501-65535  |TCP/UDP  |ビデオ会議で使用するメディア ポート範囲。  |
|フロントエンド サーバー  |Skype for Business Server Web 互換サービス  |80  |HTTP  |HTTPS が使用されない場合の、フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロントエンド サーバー  |Skype for Business Server Web 互換サービス  |443  |HTTPS  |フロントエンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロントエンド サーバー  |Skype for Business Server Web 互換サービス  |8080  |TCP および HTTP  |外部アクセスのために Web コンポーネントで使用。  |
|フロントエンド サーバー  |Web サーバー コンポーネント  |4443  |HTTPS  |Autodiscover サインインのための HTTPS (リバース プロキシから) および HTTPS フロント エンドのプール間通信。  |
|フロントエンド サーバー  |Web サーバー コンポーネント  |8060  |TCP (MTLS)  ||
|フロントエンド サーバー  |Web サーバー コンポーネント  |8061  |TCP (MTLS)  ||
|フロントエンド サーバー  |Mobility Service コンポーネント  |5086  |TCP (MTLS)  |Mobility Service の内部プロセスに使用される SIP ポート。  |
|フロントエンド サーバー  |Mobility Service コンポーネント  |5087  |TCP (MTLS)  |Mobility Service の内部プロセスに使用される SIP ポート。  |
|フロントエンド サーバー  |Mobility Service コンポーネント  |443  |HTTPS  ||
|フロントエンド サーバー  |Skype for Business Server 会議アテンダントサービス (ダイヤルイン会議)  |5064  |TCP  |ダイヤルイン会議の SIP 要求を受信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server 会議アテンダントサービス (ダイヤルイン会議)  |5072  |TCP  |応答の受信 SIP 要求 (ダイヤルイン会議) に使用されます。  |
|併置された仲介サーバーも実行するフロントエンド サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP  |フロントエンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。  |
|併置された仲介サーバーも実行するフロントエンド サーバー  |Skype for Business Server 仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロントエンド サーバー  |Skype for Business Server 仲介サービス  |5068  |TCP  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロントエンド サーバー  |Skype for Business Server 仲介サービス  |5081  |TCP  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|併置された仲介サーバーも実行するフロントエンド サーバー  |Skype for Business Server 仲介サービス  |5082  |TCP (TLS)  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server アプリケーション共有サービス  |5065  |TCP  |アプリケーション共有の SIP リッスン要求を受信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server アプリケーション共有サービス  |49152-65535  |TCP  |アプリケーション共有で使用するメディア ポート範囲。  |
|フロントエンド サーバー  |Skype for Business Server 会議のアナウンスメントサービス  |5073  |TCP  |Skype for Business Server 会議アナウンスメントサービス (ダイヤルイン会議) の受信 SIP 要求に使用されます。  |
|フロントエンド サーバー  |Skype for Business Server Call パークサービス  |5075  |TCP  |コール パーク アプリケーションの SIP 要求を受信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server の音声テストサービス  |5076  |TCP  |オーディオ テスト サービスの SIP 要求を受信するために使用。  |
|フロントエンド サーバー  |該当なし  |5066  |TCP  |発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。  |
|フロントエンド サーバー  |Skype for Business Server 応答グループサービス  |5071  |TCP  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server 応答グループサービス  |8404  |TCP (MTLS)  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロントエンド サーバー  |Skype for Business Server 帯域幅ポリシーサービス  |5080  |TCP  |音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。  |
|フロントエンド サーバー  |Skype for Business Server ファイル共有サーバーへのアクセス  |445   |SMB/TCP  | ファイル共有サーバーに保存されているアドレス帳、会議コンテンツ、およびその他のアイテムを取得するために使用されます。  |
|フロントエンド サーバー  |Skype for Business Server 帯域幅ポリシーサービス  |448  |TCP  |Skype for Business Server 帯域幅ポリシーサービスによる通話受付制御に使用されます。  |
|中央管理ストアが配置されているフロントエンドサーバー  | Skype for Business Server マスターレプリケーターエージェントサービス |445  |TCP  |Skype for Business Server を実行しているサーバーに、中央の管理ストアから構成データをプッシュするために使用されます。  |
|すべてのサーバー  |SQL ブラウザー  |1434  |UDP  |ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピー用の SQL ブラウザー  |
|すべての内部サーバー  |各種  |49152-57500  |TCP/UDP  |すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用されます。フロントエンドサーバー (Skype for Business Server 会議アテンダントサービス、skype for business Server 会議のアナウンスメントサービス、Skype for Business Server Audio/ビデオ会議サービス)、仲介サーバー。  |
|Office Web Apps サーバー  ||443  ||Skype for Business Server が Office Web Apps サーバーに接続するために使用されます。  |
|ディレクター  |Skype for Business Server のフロントエンドサービス  |5060  |TCP  |リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。  |
|ディレクター  |Skype for Business Server のフロントエンドサービス  |444  |HTTPS  <br/> TCP  |フロントエンドとディレクターの間のサーバー間通信。 さらに、クライアント証明書公開 (フロントエンドサーバー) またはクライアント証明書が既に公開されているかどうかを確認します。  |
|ディレクター  |Skype for Business Server Web 互換サービス  |80  |TCP  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。  |
|ディレクター  |Skype for Business Server Web 互換サービス  |443  |HTTPS  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|ディレクター  |Skype for Business Server のフロントエンドサービス  |5061  |TCP  |サーバー間の内部通信とクライアント接続に使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP  |フロントエンド サーバーからの要求を受信するために仲介サーバーで使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5068  |TCP  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP (MTLS)  |フロントエンド サーバーからの SIP 要求で使用。  |
|常設チャット フロントエンド サーバー  |常設チャット SIP  |5041  |TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |常設チャット Windows Communication Foundation (WCF)  |881  |TCP (TLS) および TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |常設チャット ファイル転送サービス  |443  |TCP (TLS)  ||
   
> [!NOTE]
> 一部のリモート通話コントロールシナリオでは、フロントエンドサーバーまたはディレクターと PBX の間に TCP 接続が必要です。 Skype for Business Server は TCP ポート5060を使用しなくなりましたが、リモートコールコントロールの展開時に、RCC Line Server の FQDN と、フロントエンドサーバーまたはディレクターがその TCP ポートに接続して、PBX システム。 詳細については、「Skype for Business Server 管理シェルドキュメントの**CsTrustedApplicationComputer**コマンドレット」を参照してください。
  
次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。
  
**ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー**

|ロード バランサー|ポート|プロトコル|
|:-----|:-----|:-----|
|フロントエンド サーバーのロード バランサー  |5061  |TCP (TLS)  |
|フロントエンド サーバーのロード バランサー  |444  |HTTPS  |
|フロントエンド サーバーのロード バランサー  |135  |DCOM およびリモート プロシージャ コール (RPC)  |
|フロントエンド サーバーのロード バランサー  |80  |HTTP  |
|フロントエンド サーバーのロード バランサー  |8080  |フロントエンドサーバーからのルート証明書の TCP クライアントとデバイスの取得-NTLM によって認証されたクライアントとデバイス  |
|フロントエンド サーバーのロード バランサー  |443  |HTTPS  |
|フロントエンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|フロントエンド サーバーのロード バランサー  |5072  |TCP  |
|フロントエンド サーバーのロード バランサー  |5073  |TCP  |
|フロントエンド サーバーのロード バランサー  |5075  |TCP  |
|フロントエンド サーバーのロード バランサー  |5076  |TCP  |
|フロントエンド サーバーのロード バランサー  |5071  |TCP  |
|フロントエンド サーバーのロード バランサー  |5080  |TCP  |
|フロントエンド サーバーのロード バランサー  |448  |TCP  |
|仲介サーバーのロード バランサー  |5070  |TCP  |
|フロントエンド サーバーのロード バランサー (プールで仲介サーバーも稼働する場合)  |5070  |TCP  |
|ディレクターのロード バランサー  |443  |HTTPS  |
|ディレクターのロード バランサー  |444  |HTTPS  |
|ディレクターのロード バランサー  |5061  |TCP  |
|ディレクターのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
   
DNS 負荷分散を使用するフロントエンド プールとディレクター プールでも、ハードウェア ロード バランサーを展開しておく必要があります。次の表に、これらのハードウェア ロード バランサーで開く必要があるポートを示します。
  
**DNS 負荷分散を使用する場合のハードウェア ロード バランサー**

|ロード バランサー|ポート|プロトコル|
|:-----|:-----|:-----|
|フロントエンド サーバーのロード バランサー  |80  |HTTP  |
|フロントエンド サーバーのロード バランサー  |443  |HTTPS  |
|フロントエンド サーバーのロード バランサー  |8080  |フロントエンドサーバーからのルート証明書の TCP クライアントとデバイスの取得-NTLM によって認証されたクライアントとデバイス  |
|フロントエンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|ディレクターのロード バランサー  |443  |HTTPS  |
|ディレクターのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |

**必要なクライアント ポート**

|コンポーネント|ポート|プロトコル|メモ|
|:-----|:-----|:-----|:-----|
|クライアント  |67/68  |DHCP  |Skype for Business Server でレジストラー FQDN を検索するために使用されます (つまり、DNS SRV に失敗した場合は、手動の設定が構成されていない場合)。  |
|クライアント  |443  |TCP (TLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |443  |TCP (PSOM/TLS)  |Web 会議セッションへの外部ユーザー アクセスで使用。  |
|クライアント  |443  |TCP (STUN/MSTURN)  |音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用。  |
|クライアント  |3478  |UDP (STUN/MSTURN)  |音声ビデオ セッションとメディアへの外部ユーザー アクセス (UDP) で使用。  |
|クライアント  |5061  |TCP (MTLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |6891-6901  |TCP  |Skype for Business クライアントと以前のクライアント間のファイル送信に使用されます。  |
|クライアント  |1024-65535\*  |TCP/UDP  |オーディオ ポート範囲 (少なくとも 20 個のポートが必要)。  |
|クライアント  |1024-65535\*  |TCP/UDP  |ビデオ ポート範囲 (少なくとも 20 個のポートが必要)。  |
|クライアント  |1024-65535\*  |TCP  |ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。  |
|クライアント  |1024-65535\*  |TCP  |アプリケーション共有。  |
|Aastra 6721ip 共通領域電話  <br/> Aastra 6725ip 卓上電話  <br/> HP 4110 IP 電話 (共通領域電話)  <br/> HP 4120 IP 電話 (卓上電話)  <br/> Polycom CX500 IP 共通領域電話  <br/> Polycom CX600 IP 卓上電話  <br/> Polycom CX700 IP 卓上電話  <br/> Polycom CX3000 IP 会議電話  |67/68  |DHCP  |表示されているデバイスで、Skype for Business Server の証明書、プロビジョニング FQDN、レジストラー FQDN を見つけるために使われます。  |
   
\*これらのメディアの種類に対して特定のポートを構成するには、CsConferencingConfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、ClientMediaPortRange parameters) を使用します。
  
> [!NOTE]
> Skype for Business クライアントのセットアッププログラムは、クライアントコンピューターに必要なオペレーティングシステムファイアウォール例外を自動的に作成します。 

> [!NOTE]
> 外部ユーザーアクセスに使用されるポートは、クライアントが組織のファイアウォールを通過する必要がある場合 (たとえば、他の組織によってホストされている外部通信や会議など) に必要です。 
  
## <a name="ipsec-exceptions"></a>IPSec 例外

企業ネットワーク上でインターネット プロトコル セキュリティ (IPsec) (IETF RFC 4301 ～ 4309 を参照) を導入している場合、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートの範囲に対して IPsec を無効にする必要があります。この操作を行うと、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。
  
次の表に、推奨される IPsec 例外設定を示します。 
  
**推奨される IPSec 例外設定**

|ルール名|発信元 IP アドレス|送信先 IP アドレス|プロトコル|送信元ポート|宛先ポート|認証要件|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|内部音声ビデオ エッジ サーバー/受信  |任意  |内部音声ビデオ エッジ サーバー  |UDP および TCP  |任意   |任意  |認証しない  |
|外部音声ビデオ エッジ サーバー/受信  |任意  |外部音声ビデオ エッジ サーバー  |UDP および TCP  |任意   |任意  |認証しない  |
|内部音声ビデオ エッジ サーバー/送信  |内部音声ビデオ エッジ サーバー  |任意  |UDP &amp; TCP  |任意   |任意  |認証しない  |
|外部音声ビデオ エッジ サーバー/送信  |外部音声ビデオ エッジ サーバー  |任意  |UDP および TCP  |任意   |任意  |認証しない  |
|仲介サーバー/受信  |任意  |仲介  <br/> サーバー  |UDP および TCP  |任意   |任意  |認証しない  |
|仲介サーバー/送信  |仲介  <br/> サーバー  |任意  |UDP および TCP  |任意   |任意  |認証しない  |
|会議アテンダント/受信  |任意  |会議アテンダントを実行するフロントエンド サーバー  |UDP および TCP  |任意   |任意  |認証しない  |
|会議アテンダント/送信  |会議アテンダントを実行するフロントエンド サーバー  |任意  |UDP および TCP  |任意   |任意  |認証しない  |
|音声ビデオ会議サーバー/受信  |任意  |フロントエンド サーバー  |UDP および TCP  |任意   |任意  |認証しない  |
|音声ビデオ会議/送信  |フロントエンド サーバー  |任意  |UDP および TCP  |任意   |任意  |認証しない  |
|Exchange/受信  |任意  |Exchange ユニファイド メッセージング  |UDP および TCP  |任意   |任意  |認証しない  |
|アプリケーション共有サーバー/受信  |任意  |アプリケーション共有サーバー  |TCP  |任意   |任意  |認証しない  |
|アプリケーション共有サーバー/送信  |アプリケーション共有サーバー  |任意  |TCP  |任意   |任意  |認証しない  |
|Exchange/送信  |Exchange ユニファイド メッセージング  |任意  |UDP および TCP  |任意   |任意  |認証しない  |
|クライアント  |任意   |任意  |UDP  |指定メディア ポート範囲  |任意  |認証しない  |
