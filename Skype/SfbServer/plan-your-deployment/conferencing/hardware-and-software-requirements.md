---
title: Skype for Business Server での会議のハードウェアおよびソフトウェア要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: '概要: このトピックでは、Skype for Business Server での会議のハードウェアとソフトウェアの要件について説明します。'
ms.openlocfilehash: 0d09e0e85e7059e0a761b2822f963765751623e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815985"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Skype for Business Server での会議のハードウェアおよびソフトウェア要件

**概要:** このトピックでは、Skype for Business Server での会議のハードウェアとソフトウェアの要件について説明します。

ここでは、Web 会議、音声ビデオ (A/V) 会議、ダイヤルイン会議、およびインスタント メッセージング (IM) 会議のハードウェアおよびソフトウェア要件について説明します。 すべての会議の機能はフロントエンド サーバー上で実行されますが、以下の図に示すように、さまざまな種類の会議に対して追加の要件があります。

たとえば、ダイヤルイン会議を許可する場合は、仲介サーバーと、公衆交換電話網 (PSTN) に接続するためのゲートウェイを展開する必要があります。 Web 会議を許可する場合は、Skype for Business Server が Office Web Apps サーバーに接続できることを確認する必要があります。 外部ユーザーが会議に参加できるようにする場合は、エッジ サーバーを展開する必要があります。

**会議の機能と要件**

![会議のコンポーネント](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 トポロジの考慮事項の詳細については、「 [Skype For Business Server の会議トポロジを計画する](conferencing-topology.md)」を参照してください。

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>フロントエンド サーバーのハードウェアおよびソフトウェア要件

Web 会議、A/V 会議、ダイヤルイン会議、IM 会議はすべて、フロントエンドサーバーと連携しているため、サーバーハードウェアとソフトウェアの要件は、フロントエンドサーバーの場合と同じです。 これらの要件の詳細については、「skype for business server [2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」 [2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)および「skype for Business server [2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。

## <a name="requirements-for-web-conferencing"></a>Web 会議の要件

Web 会議を有効にすることにした場合、次のものを計画する必要があります。

- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。

- 会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバーとの統合。

### <a name="file-store"></a>ファイル ストア

Skype for Business Server web 会議サービスは、会議中に共有されたコンテンツをファイルストアに保存します。 展開の一環として、Standard Edition server または Enterprise Edition のフロントエンドプールのファイルストアとして使用するファイル共有を指定する必要があります。 ファイルストアには既存のファイル共有を使用できます。また、ファイル共有が置かれているファイルサーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。 詳細については、「 [Skype For Business Server でファイル共有を作成](../../deploy/install/create-a-file-share.md)する」を参照してください。 Web 会議サービスによって、コンテンツがファイルストアに保存される前に暗号化されます。

Skype for Business Server は、直接接続されたストレージ (DAS) またはストレージエリアネットワーク (SAN) 上でのファイル共有の使用をサポートします。これには、分散ファイルシステム (DFS)、およびファイルストア用の冗長な独立したディスク (RAID) が含まれます。 Skype for Business Server の展開ウィザードでファイル共有の場所が定義された後、Skype for Business Server は、次のようなファイル共有内にフォルダー構造を作成します。

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。

### <a name="office-web-apps-server"></a>Office Web Apps サーバー

Web 会議機能を使用するには、Office Web Apps サーバーをインストールし、Office Web Apps サーバーと通信できるように Skype for Business Server を構成する必要があります。

Office Web Apps サーバーは、Skype for Business Server、SQL Server、またはその他のサーバーアプリケーションを実行していないスタンドアロンコンピューターにインストールする必要があります。 (そのコンピューターに Office のバージョンがインストールされていない必要があります)。Office Web Apps サーバーを実行するために使用されるコンピューターには、特定のソフトウェアセット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要もあります。 これらの要件と、証明書とインターネットインフォメーションサービス (IIS) を構成する方法については、 [Microsoft Office Web Apps の展開 web サイト](https://go.microsoft.com/fwlink/p/?linkid=257525)で詳しく説明します。

Office Web Apps サーバーで動作するように Skype for Business Server を構成する方法については、「 [skype For Business server で Office Web Apps サーバーとの統合を構成](../../deploy/deploy-conferencing/office-web-app-server.md)する」を参照してください。

## <a name="requirements-for-audio-and-video-conferencing"></a>音声ビデオ会議の要件

音声ビデオ会議を計画する場合、組織で必要な種類の会議メディアで求められるネットワーク帯域幅について理解する必要があります。 これには音声、ビデオ、パノラマ ビデオが含まれる可能性があります。 十分なネットワーク帯域幅がない場合、ユーザー エクスペリエンスが大幅に低下する可能性があります。

会議用の音声およびビデオ機能の計画の詳細については、「[Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md)」を参照してください。

通話受付管理 (CAC) を使用して、音声ビデオ会議で使用されるネットワーク帯域幅を管理できます。 これは、中央サイトとブランチ サイト間の帯域幅リンクの制限など、制限のあるネットワークで重要になります。 詳細については、「 [Skype For Business Server での通話受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)」を参照してください。

電話会議をネットワークに展開する場合、ユーザーが会議に参加するにはヘッドセットなどのオーディオ デバイスが必要です。 ビデオ会議を展開する場合は、Web カメラなどのビデオ デバイスをユーザー用に展開する必要があります。 オーディオ デバイスまたはビデオ デバイスのいずれの場合も、デバイスの展開とユーザー トレーニングを検討することが重要です。 詳細については、「[クライアントとデバイスの計画](../../plan-your-deployment/clients-and-devices/clients-and-devices.md)」を参照してください。 最適なユーザー エクスペリエンスを実現するには、Microsoft で認定された統合コミュニケーション (UC) デバイスをすべてのデバイスの種類に使用することをお勧めします。 UC 認定デバイスの詳細については、「 [Skype For business の電話とデバイス](https://go.microsoft.com/fwlink/?LinkId=619916)」を参照してください。

## <a name="requirements-for-dial-in-conferencing"></a>ダイヤルイン会議の要件

ダイヤルイン会議は、さまざまなコンポーネントを含む Skype for Business Server 会議ワークロードのオプションの機能です。 一部のコンポーネントは、ダイヤルイン会議に固有であり、一部はエンタープライズボイスコンポーネントです。 このセクションでは、ダイヤルイン会議に必要なコンポーネントの要件について説明します。 仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイの要件の詳細については、「 [skype For Business server の仲介サーバーコンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)」と「 [Skype for Business Server のトポロジビルダーで仲介サーバーを展開する](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)」を参照してください。

### <a name="required-components"></a>必要なコンポーネント

ダイヤルイン会議を構成するには、事前に次の Skype for Business Server コンポーネントをインストールする必要があります。

- 統合コミュニケーション アプリケーション サービス (UCAS) (アプリケーション サービスと呼ばれます)

- 会議アテンダント アプリケーション

- 会議アナウンス アプリケーション

- ダイヤルイン会議設定 Web ページ

- 少なくとも 1 つの仲介サーバーと少なくとも 1 つの PSTN ゲートウェイ

ダイヤルイン会議、アプリケーションサービス、会議アテンダントアプリケーション、会議アナウンスメントアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件があります。 詳細については、「[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。

会議アテンダントアプリケーションと会議アナウンスメントアプリケーションでは、Windows Media Format Runtime がフロントエンドサーバーにインストールされている必要があります。 Windows Media フォーマット ランタイムは、保留音、録音済みの名前、案内で使用される Windows Media オーディオ (WMA) ファイルの再生に必要です。 Windows Server 2012 または Windows Server 2012 R2 にインストールする場合 (推奨)、Windows Media 形式ランタイムを取得するには Microsoft メディアファンデーションをインストールする必要があります。 Windows Server 2012 よりも前のバージョンの Windows Server にインストールする場合、Windows Media フォーマット ランタイムを入手するには、Windows デスクトップ エクスペリエンスをインストールしておく必要があります。

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議の音声ファイル要件

Skype for Business Server は、ダイヤルイン会議の音声メッセージや音楽のカスタマイズをサポートしていません。 ただし、既定のオーディオファイルを変更する必要がある強いビジネスニーズがある場合は、「Microsoft サポート技術情報の記事961177」を参照してください。[音声メッセージのカスタマイズ方法、またはダイヤルイン電話会議の音楽ファイルをカスタマイズする方法](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)について説明します。

[Microsoft Lync Server 会議アテンダントのカスタム音声指示](https://go.microsoft.com/fwlink/p/?LinkId=396880)管理ユーティリティを使用することもできます。これにより、管理者は、電話の発信者が Skype for business 会議にカスタムプロンプトを使用して Skype for business 会議に参加するときに使用する既定の音声プロンプトを、別の会議エントリの操作を提供することができます。 カスタム音声プロンプトは、Enterprise または Standard Edition サーバーにインストールできます。

会議アテンダントアプリケーションと会議アナウンスメントアプリケーションには、音楽の保留、記録された名前、およびオーディオプロンプトファイルの次の要件があります。

- Windows Media Audio (WMA) ファイル形式

- 16 ビット モノラル

- 48 Kbps 2-pass CBR (固定ビット レート)

- -24DB の音声レベル

### <a name="user-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のユーザー要件

ダイヤルイン会議ユーザーは、そのアカウントに固有の電話番号または内線番号を割り当てておく必要があります。 この要件によりダイヤルイン会議中の認証が可能になります。 エンタープライズユーザー (つまり、組織内で Active Directory ドメインサービスの資格情報と Skype for Business Server アカウントを持っているユーザー) は、電話番号 (または内線番号) と暗証番号 (PIN) を入力して、会議にダイヤルインします。認証されたユーザー。

## <a name="port-requirements-for-conferencing"></a>会議のポート要件

会議機能を使用するためには、Skype for Business Server で特定のポートが開かれている必要があります。 次の表に、会議のポート要件の一覧を示します。 すべてのポート要件の詳細については、「[サーバーのポートとプロトコルの要件](../../plan-your-deployment/network-requirements/ports-and-protocols.md)」を参照してください。

**必要なサーバー ポート**


|**サーバーの役割**|**サービス名**|**ポート**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|
|フロントエンド サーバー  <br/> |Skype for Business Server IM 会議サービス  <br/> |5062  <br/> |TCP  <br/> |インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server Web 会議サービス  <br/> |8057  <br/> |TCP (TLS)  <br/> |クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server Web 会議の互換性サービス  <br/> |8058  <br/> |TCP (TLS)  <br/> |Live Meeting クライアントと以前のバージョンの Skype for Business Server からの永続的な共有オブジェクトモデル (PSOM) 接続をリッスンするために使用されます。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server の音声/ビデオ会議サービス  <br/> |5063  <br/> |TCP  <br/> |音声ビデオ会議の SIP 要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server の音声/ビデオ会議サービス  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |ビデオ会議で使用するメディア ポート範囲。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server 会議アテンダントサービス (ダイヤルイン会議)  <br/> |5064  <br/> |TCP  <br/> |ダイヤルイン会議の SIP 要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server 会議アテンダントサービス (ダイヤルイン会議)  <br/> |5072  <br/> |TCP  <br/> |応答の受信 SIP 要求 (ダイヤルイン会議) に使用されます。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |49152-65535  <br/> |TCP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
|フロントエンド サーバー  <br/> |Skype for Business Server 会議のアナウンスメントサービス  <br/> |5073  <br/> |TCP  <br/> |Skype for Business Server 会議アナウンスメントサービス (ダイヤルイン会議) の受信 SIP 要求に使用されます。  <br/> |
|すべての内部サーバー  <br/> |各種  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用されます。フロントエンドサーバー (Skype for Business Server 会議アテンダントサービス、skype for business server 会議のアナウンスメントサービス、Skype for Business server の音声/ビデオ会議サービス、および仲介サーバー)。  <br/> |
|Office Web Apps サーバー  <br/> ||443  <br/> ||Skype for Business Server が Office Web Apps サーバーに接続するために使用されます。  <br/> |

**必要なクライアントポート**


|**ポート**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Web 会議セッションへの外部ユーザー アクセスで使用  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |音声ビデオ セッションとメディアへの外部ユーザー アクセス (UDP) で使用。  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |オーディオ ポート範囲 (少なくとも 20 個のポートが必要)。  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |ビデオ ポート範囲 (少なくとも 20 個のポートが必要)。  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |アプリケーション共有  <br/> |


