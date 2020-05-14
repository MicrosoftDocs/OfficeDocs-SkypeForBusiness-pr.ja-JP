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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: '概要: Skype for Business Server を実装する前に、ポートの使用に関する考慮事項を確認してください。'
ms.openlocfilehash: 09b0d187195faa0aa4b5278456991d9223427f9d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220387"
---
# <a name="port-and-protocol-requirements-for-servers"></a>サーバーのポートとプロトコルの要件
 
**概要:** Skype for Business Server を実装する前に、ポートの使用に関する考慮事項を確認します。
  
Skype for Business Server では、外部および内部ファイアウォール上の特定のポートを開く必要があります。 さらに、組織でインターネット プロトコル セキュリティ (IPsec) が展開されている場合は、音声、ビデオ、およびパノラマ ビデオの配信に使用するポートの範囲に対して IPsec を無効にする必要があります。 
  
これは最初は少し困難に思えるかもしれませんが、これを計画するには、 [Skype For Business Server 2015 計画ツール](https://go.microsoft.com/fwlink/p/?LinkID=282725)を使用して行うことができます。 使用する予定の機能に関するウィザードの質問について説明した後は、エッジ管理レポートでファイアウォールレポートを表示し、そこに一覧表示されている情報を使用してファイアウォールルールを作成できます。 また、使用されている名前と IP アドレスの多くを調整することもできます。詳細については、「 [Review The Firewall Report](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report)」を参照してください。 エッジ管理レポートは、Excel スプレッドシートにエクスポートでき、ファイアウォールレポートはファイル内のワークシートの1つになることに注意してください。 
  
また、「 [Skype For business 2015 Server の技術ダイアグラム](../../technical-diagrams.md)」の記事に記載されているプロトコルワークロードのポスターを参照すると、これらの表に記載されている情報を図の形式で見つけることができます。
> [!NOTE]
> - Skype for Business Online (Microsoft 365 または Office 365) を実装している場合は[、「microsoft 365」および「office 365 の url と IP アドレスの範囲](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)」を参照してください。 ハイブリッド環境では、このトピックを参照し、[ハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)する必要があります。
> - ハードウェアまたはソフトウェアファイアウォールを使用することはできますが、特定のモデルやバージョンは必要ありません。 重要なのは、どのポートがホワイトリストされているのか、ファイアウォールが Skype for Business Server の機能を損なわないようにするためです。
  
## <a name="port-and-protocol-details"></a>ポートとプロトコルの詳細

このセクションでは、Skype for Business Server 展開のサーバー、ロードバランサー、およびクライアントで使用されるポートとプロトコルの概要について説明します。
  
> [!NOTE]
> Skype for Business Server を起動すると、Windows ファイアウォールで必要なポートが開きます。 Windows ファイアウォールは、多くの通常のアプリケーションで既に実行されていますが、使用されていない場合は、Skype for Business Server はそれがなく機能します。 
  
エッジコンポーネントのファイアウォール構成の詳細については、「 [Skype For Business server のエッジサーバーのシナリオ 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md)」を参照してください。 
  
次の表に、各内部サーバー役割で開く必要のあるポートの一覧を示します。 
  
**必要なサーバー ポート (サーバー役割別)**

|サーバーの役割|サービス名|ポート|プロトコル|メモ|
|:-----|:-----|:-----|:-----|:-----|
|すべてのサーバー  |SQL ブラウザー  |1434  |受信  |中央管理ストアデータベースのローカルにレプリケートされたコピーの SQL ブラウザー。  |
|フロント エンド サーバー  |Skype for Business Server のフロントエンドサービス  |5060  |TCP  |リモート通話コントロール サーバーなどの Standard Edition サーバーとフロント エンド サーバーで、信頼されたサービスへの静的ルートの場合にオプションとして使用。  |
|フロント エンド サーバー  |Skype for Business Server のフロントエンドサービス  |5061  | TCP (TLS) |サーバー間のすべての内部 SIP 通信 (MTLS)、サーバーとクライアントの間の SIP 通信 (TLS)、およびフロント エンド サーバーと仲介サーバーの間の SIP 通信 (MTLS) において、Standard Edition サーバーとフロント エンド プールで使用。 監視サーバーとの通信にも使用されます。  |
| フロント エンド サーバー |Skype for Business Server のフロントエンドサービス  |444  | HTTPS <br/> TCP  |フォーカス (会議の状態を管理する Skype for Business Server コンポーネント) と個々のサーバーとの間の HTTPS 通信に使用されます。  <br/> このポートは、存続可能ブランチアプライアンスとフロントエンドサーバー間の TCP 通信にも使用されます。  |
|フロント エンド サーバー  |Skype for Business Server のフロントエンドサービス  |135  |DCOM およびリモート プロシージャ コール (RPC)  |ユーザーの移行、ユーザー レプリケーター同期、およびアドレス帳同期などの DCOM ベースの操作で使用。  |
|フロント エンド サーバー  |Skype for Business Server IM 会議サービス  |5062  |TCP  |インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 会議サービス  |8057  |TCP (TLS)  |クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 会議互換性サービス  |8058  |TCP (TLS)  |Live Meeting クライアントおよび以前のバージョンの Skype for Business Server からの、永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。  |
|フロント エンド サーバー  |Skype for Business Server の音声ビデオ会議サービス  |5063  |TCP  |音声ビデオ会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server の音声ビデオ会議サービス  |57501-65535  |TCP/UDP  |ビデオ会議で使用するメディア ポート範囲。  |
|フロント エンド サーバー  |Skype for Business Server Web 互換性サービス  |80  |HTTP  |HTTPS が使用されない場合の、フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 互換性サービス  |443  |HTTPS  |フロント エンド サーバーから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|フロント エンド サーバー  |Skype for Business Server Web 互換性サービス  |8080  |TCP および HTTP  |外部アクセスのために web コンポーネントによって使用されます。  |
|フロント エンド サーバー  |Web サーバーコンポーネント  |4443  |HTTPS  |自動検出サインインの HTTPS (リバースプロキシから) および HTTPS フロントエンドプール間通信。  |
|フロント エンド サーバー  |Web サーバーコンポーネント  |8060  |TCP (MTLS)  ||
|フロント エンド サーバー  |Web サーバーコンポーネント  |8061  |TCP (MTLS)  ||
|フロント エンド サーバー  |Mobility Services コンポーネント  |5086  |TCP (MTLS)  |Mobility Services 内部プロセスで使用される SIP ポート  |
|フロント エンド サーバー  |Mobility Services コンポーネント  |5087  |TCP (MTLS)  |Mobility Services 内部プロセスで使用される SIP ポート  |
|フロント エンド サーバー  |Mobility Services コンポーネント  |443  |HTTPS  ||
|フロント エンド サーバー  |Skype for Business Server 会議アテンダントサービス (ダイヤルイン会議)  |5064  |TCP  |ダイヤルイン会議の SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server 会議アテンダントサービス (ダイヤルイン会議)  |5072  |TCP  |アテンダント (ダイヤルイン会議) の SIP 要求を受信するために使用されます。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP  |フロント エンド サーバーから仲介サーバーへの要求を受信するために仲介サーバーで使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5068  |TCP  |PSTN ゲートウェイから仲介サーバーへの SIP 要求を受信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5081  |TCP  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|併置された仲介サーバーも実行するフロント エンド サーバー  |Skype for Business Server 仲介サービス  |5082  |TCP (TLS)  |仲介サーバーから PSTN ゲートウェイへの SIP 要求を送信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server アプリケーション共有サービス  |5065  |TCP  |アプリケーション共有の SIP リッスン要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server アプリケーション共有サービス  |49152-65535  |TCP  |アプリケーション共有で使用するメディア ポート範囲。  |
|フロント エンド サーバー  |Skype for Business Server 会議アナウンスサービス  |5073  |TCP  |Skype for Business Server 会議アナウンスサービス (ダイヤルイン会議) の SIP 要求を受信するために使用されます。  |
|フロント エンド サーバー  |Skype for Business Server コールパークサービス  |5075  |TCP  |コール パーク アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server Audio Test service  |5076  |TCP  |オーディオ テスト サービスの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |該当なし  |5066  |TCP  |発信 Enhanced 9-1-1 (E9-1-1) ゲートウェイで使用。  |
|フロント エンド サーバー  |Skype for Business Server Response Group service  |5071  |TCP  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server Response Group service  |8404  |TCP (MTLS)  |応答グループ アプリケーションの SIP 要求を受信するために使用。  |
|フロント エンド サーバー  |Skype for Business Server 帯域幅ポリシーサービス  |5080  |TCP  |音声ビデオ エッジ TURN トラフィックの帯域幅ポリシー サービスによる通話受付管理で使用。  |
|フロント エンド サーバー  |Skype for Business Server ファイル共有サーバーアクセス  |445   |SMB/TCP  | ファイル共有サーバーに格納されているアドレス帳、会議コンテンツ、およびその他のアイテムを取得するために使用されます。  |
|フロント エンド サーバー  |Skype for Business Server 帯域幅ポリシーサービス  |448  |TCP  |Skype for Business Server 帯域幅ポリシーサービスによる通話受付管理に使用されます。  |
|中央管理ストアが存在するフロントエンドサーバー  | Skype for Business Server のマスターレプリケーターエージェントサービス |445  |TCP  |中央管理ストアから Skype for Business Server を実行しているサーバーに構成データをプッシュするために使用されます。  |
|すべてのサーバー  |SQL ブラウザー  |1434  |受信  |ローカルの SQL Server インスタンスの中央管理ストアデータのローカルにレプリケートされたコピーのための SQL ブラウザー  |
|すべての内部サーバー  |各種  |49152-57500  |TCP/UDP  |すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用します。フロントエンドサーバー (Skype for Business Server 会議アテンダントサービス、skype for business Server 会議アナウンスサービス、Skype for business Server の音声ビデオ会議サービス、および仲介サーバー)。  |
|Office Web Apps サーバー  ||443  ||Skype for Business Server が Office Web Apps サーバーに接続するために使用します。  |
|レ  |Skype for Business Server のフロントエンドサービス  |5060  |TCP  |リモート通話コントロール サーバーなど、信頼されたサービスへの静的ルートの場合にオプションで使用。  |
|レ  |Skype for Business Server のフロントエンドサービス  |444  |HTTPS  <br/> TCP  |フロントエンドとディレクターの間のサーバー間通信。 さらに、クライアント証明書を (フロントエンドサーバーに) 公開するか、クライアント証明書が既に公開されているかどうかを確認します。  |
|レ  |Skype for Business Server Web 互換性サービス  |80  |TCP  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への初期通信に使用。通常の動作では HTTPS トラフィックに切り替わり、ポート 443 およびプロトコル TCP を使用します。  |
|レ  |Skype for Business Server Web 互換性サービス  |443  |HTTPS  |ディレクターから Web ファーム FQDN (IIS Web コンポーネントで使用される URL) への通信に使用。  |
|レ  |Skype for Business Server のフロントエンドサービス  |5061  |TCP  |サーバー間の内部通信とクライアント接続に使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP  |フロント エンド サーバーからの要求を受信するために仲介サーバーで使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5067  |TCP (TLS)  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5068  |TCP  |PSTN ゲートウェイからの SIP 要求を受信するために使用。  |
|仲介サーバー  |Skype for Business Server 仲介サービス  |5070  |TCP (MTLS)  |フロント エンド サーバーからの SIP 要求で使用。  |
|常設チャット フロントエンド サーバー  |常設チャット SIP  |5041  |TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |常設チャット Windows Communication Foundation (WCF)  |881  |TCP (TLS) と TCP (MTLS)  ||
|常設チャット フロントエンド サーバー  |常設チャットのファイル転送サービス  |443  |TCP (TLS)  ||
   
> [!NOTE]
> リモート通話コントロールのシナリオによっては、フロントエンドサーバーまたはディレクターと PBX との間に TCP 接続が必要な場合があります。 Skype for Business Server は TCP ポート5060を使用しなくなりましたが、リモート通話コントロールの展開時には、RCC Line サーバーの FQDN と、そのフロントエンドサーバーまたはディレクターが PBX システムに接続するために使用する TCP ポートを関連付ける信頼されたサーバー構成を作成します。 詳細については、「Skype for Business Server Management Shell」のドキュメントの「 **CsTrustedApplicationComputer**コマンドレット」を参照してください。
  
次の表に、(DNS 負荷分散ではない) ハードウェア負荷分散のみを使用するプールでハードウェア ロード バランサーを開くために必要なポートを示します。
  
**ハードウェア負荷分散のみを使用する場合のハードウェア ロード バランサー**

|ロード バランサー|ポート|プロトコル|
|:-----|:-----|:-----|
|フロント エンド サーバーのロード バランサー  |5061  |TCP (TLS)  |
|フロント エンド サーバーのロード バランサー  |444  |HTTPS  |
|フロント エンド サーバーのロード バランサー  |135  |DCOM およびリモート プロシージャ コール (RPC)  |
|フロント エンド サーバーのロード バランサー  |80  |HTTP  |
|フロント エンド サーバーのロード バランサー  |8080  |TCP-フロントエンドサーバーからのクライアントとデバイスのルート証明書取得-NTLM で認証されたクライアントとデバイス  |
|フロント エンド サーバーのロード バランサー  |443  |HTTPS  |
|フロント エンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|フロント エンド サーバーのロード バランサー  |5072  |TCP  |
|フロント エンド サーバーのロード バランサー  |5073  |TCP  |
|フロント エンド サーバーのロード バランサー  |5075  |TCP  |
|フロント エンド サーバーのロード バランサー  |5076  |TCP  |
|フロント エンド サーバーのロード バランサー  |5071  |TCP  |
|フロント エンド サーバーのロード バランサー  |5080  |TCP  |
|フロント エンド サーバーのロード バランサー  |448  |TCP  |
|仲介サーバーのロードバランサー  |5070  |TCP  |
|フロントエンドサーバーのロードバランサー (プールが仲介サーバーも実行している場合)  |5070  |TCP  |
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
|フロント エンド サーバーのロード バランサー  |8080  |TCP-フロントエンドサーバーからのクライアントとデバイスのルート証明書取得-NTLM で認証されたクライアントとデバイス  |
|フロント エンド サーバーのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |
|ディレクターのロード バランサー  |443  |HTTPS  |
|ディレクターのロード バランサー  |4443  |HTTPS (リバース プロキシから)  |

**必要なクライアント ポート**

|コンポーネント|ポート|プロトコル|メモ|
|:-----|:-----|:-----|:-----|
|クライアント  |67/68  |DHCP  |Skype for Business Server がレジストラーの FQDN を検索するために使用します (つまり、DNS SRV に障害が発生し、手動設定が構成されていない場合)。  |
|クライアント  |443  |TCP (TLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |443  |TCP (PSOM/TLS)  |Web 会議セッションへの外部ユーザー アクセスで使用。  |
|クライアント  |443  |TCP (STUN/MSTURN)  |音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用  |
|クライアント  |3478  |UDP (STUN/MSTURN)  |音声ビデオセッションおよびメディアへの外部ユーザーアクセスに使用されます (UDP)  |
|クライアント  |5061  |TCP (MTLS)  |外部ユーザー アクセスのクライアントとサーバー間の SIP トラフィックで使用。  |
|クライアント  |6891-6901  |TCP  |Skype for Business クライアントと以前のクライアント間のファイル転送に使用されます。  |
|クライアント  |1024-65535\*  |TCP/UDP  |オーディオ ポート範囲 (少なくとも 20 個のポートが必要)  |
|クライアント  |1024-65535\*  |TCP/UDP  |ビデオ ポート範囲 (少なくとも 20 個のポートが必要)  |
|クライアント  |1024-65535\*  |TCP  |ピアツーピア ファイル転送 (会議ファイル転送の場合、クライアントは PSOM を使用)。  |
|クライアント  |1024-65535\*  |TCP  |アプリケーション共有。  |
|Aastra 6721ip 共通領域電話  <br/> Aastra 6725ip 卓上電話  <br/> HP 4110 IP 電話 (共通領域電話)  <br/> HP 4120 IP 電話 (卓上電話)  <br/> Polycom CX500 IP 共通領域電話  <br/> Polycom CX600 IP 卓上電話  <br/> Polycom CX700 IP 卓上電話  <br/> Polycom CX3000 IP 会議電話  |67/68  |DHCP  |Skype for Business Server 証明書、プロビジョニング FQDN、レジストラー FQDN を検索するために、リストされているデバイスによって使用されます。  |
   
\*これらのメディアの種類に対して特定のポートを構成するには、Get-csconferencingconfiguration コマンドレット (ClientMediaPortRangeEnabled、ClientMediaPort、および ClientMediaPortRange パラメーター) を使用します。
  
> [!NOTE]
> Skype for Business クライアントのセットアッププログラムは、クライアントコンピューター上で必要なオペレーティングシステムファイアウォール例外を自動的に作成します。 

> [!NOTE]
> 外部ユーザーアクセスに使用されるポートは、クライアントが組織のファイアウォールを通過する必要のあるすべてのシナリオ (たとえば、他の組織によってホストされる外部の通信や会議) に必要です。 
  
## <a name="ipsec-exceptions"></a>IPsec 例外

インターネットプロトコルセキュリティ (IPsec) (IETF RFC 4301-4309 を参照) が展開されているエンタープライズネットワークでは、オーディオ、ビデオ、およびパノラマビデオの配信に使用するポートの範囲内で IPsec を無効にする必要があります。 これにより、IPsec のネゴシエーションによってメディア用ポートの割り当てに遅延が生じるのを避けることができます。
  
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
|音声ビデオ会議サーバー/受信  |任意  |フロント エンド サーバー  |UDP および TCP  |任意  |任意  |認証しない  |
|音声ビデオ会議/送信  |フロントエンド サーバー  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|Exchange/受信  |任意  |Exchange ユニファイド メッセージング  |UDP および TCP  |任意  |任意  |認証しない  |
|アプリケーション共有サーバー/受信  |任意  |アプリケーション共有サーバー  |TCP  |任意  |任意  |認証しない  |
|アプリケーション共有サーバー/送信  |アプリケーション共有サーバー  |任意  |TCP  |任意  |任意  |認証しない  |
|Exchange/送信  |Exchange ユニファイド メッセージング  |任意  |UDP および TCP  |任意  |任意  |認証しない  |
|クライアント  |任意  |任意  |受信  |指定メディア ポート範囲  |任意  |認証しない  |
