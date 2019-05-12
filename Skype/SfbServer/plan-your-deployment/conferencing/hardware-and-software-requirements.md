---
title: ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: '概要: ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件の詳細については、このトピックを読みます。'
ms.openlocfilehash: 26917b3360f5e561d6484efda9b9cae76df15065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897983"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件

**の概要:** ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件の詳細については、このトピックを参照してください。

ここでは、Web 会議、音声ビデオ (A/V) 会議、ダイヤルイン会議、およびインスタント メッセージング (IM) 会議のハードウェアおよびソフトウェア要件について説明します。 すべての会議の機能はフロントエンド サーバー上で実行されますが、以下の図に示すように、さまざまな種類の会議に対して追加の要件があります。

たとえば、会議にダイヤルインを許可するには、仲介サーバーおよび公衆交換電話網 (PSTN) に接続するためのゲートウェイを展開する必要があります。 Web 会議を許可する場合は、Skype のビジネス サーバーは、Office Web アプリケーション サーバーに接続できるようにする必要があります。 外部ユーザーが会議に参加できるようにする場合は、エッジ サーバーを展開する必要があります。

**会議の機能と要件**

![会議のコンポーネント](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 トポロジに関する考慮事項の詳細については、「 [Business Server Skype の会議トポロジを計画する](conferencing-topology.md)」を参照してください。

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>フロントエンド サーバーのハードウェアおよびソフトウェア要件

Web 会議、A/V 会議、ダイヤルイン会議、および IM 会議は、すべて同じ場所にフロント エンド サーバーとすると、サーバーのハードウェアおよびソフトウェアの要件は、フロント エンド サーバーと同じです。 これらの要件の詳細については、[ビジネス サーバー 2015 の Skype のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)と[ビジネス サーバー 2015 の Skype の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)や[ビジネス サーバー 2019 の Skype のサーバーの要件](../../../SfBServer2019/plan/system-requirements.md)を参照してください。

## <a name="requirements-for-web-conferencing"></a>Web 会議の要件

Web 会議を有効にすることにした場合、次のものを計画する必要があります。

- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。

- 会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバーとの統合。

### <a name="file-store"></a>ファイル ストア

Business Server web 会議サービスの Skype では、ファイル ストア内の会議中に共有されているコンテンツを格納します。 展開の一環として、Standard Edition サーバーまたはエンタープライズ エディションのフロント エンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。 ファイル ストアの既存のファイル共有を使用することができます。 またはファイル共有に配置するのになっているファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイルの共有のフォルダー名を指定することで新しいファイルの共有を指定できます。 詳細については、 [Skype のビジネス サーバーでファイル共有を作成](../../deploy/install/create-a-file-share.md)を参照してください。 ファイル ストアにコンテンツを格納する前に、web 会議サービスは、コンテンツを暗号化します。

ビジネス サーバーのサポート ファイルを使用するの Skype では、直接接続型ストレージ (DAS) またはストレージ エリア ネットワーク (SAN)、分散ファイル システム (DFS) を含むのいずれかを共有し、ファイルの独立したディスク (RAID) の冗長な配列に格納します。 ビジネス サーバーの展開ウィザードの Skype は、ファイル共有の場所を定義した後 Skype ビジネス サーバーの作成ファイル共有内のフォルダー構造に似ています。

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。

### <a name="office-web-apps-server"></a>Office Web Apps サーバー

Web 会議機能を使用するには、Office Web アプリケーション サーバーをインストールして、Office Web アプリケーション サーバーと通信するサーバーをビジネス用の Skype を構成する必要があります。

ビジネス サーバー、SQL Server、またはその他のサーバー アプリケーションの Skype が実行されていないスタンドアロン コンピューターでは、office Web アプリケーション サーバーをインストールしてください。 (存在しないことをそのコンピューターにインストールされている Office のすべてのバージョン。)Office Web アプリケーション サーバーを実行するために使用する任意のコンピューターは、(.NET Framework 4.5、Windows PowerShell 3.0 など) がインストールされているソフトウェアの特定のセットも必要です。 証明書とインターネット インフォメーション サービス (IIS) の構成に関する情報と、これらの要件については、 [Microsoft Office Web アプリケーションの展開の web サイト](https://go.microsoft.com/fwlink/p/?linkid=257525)で詳細に説明します。

Office Web アプリケーション サーバーで動作するサーバーをビジネス用の Skype を構成する方法の詳細については、 [Skype ビジネス サーバー用に Office の Web アプリケーション サーバーと構成の統合](../../deploy/deploy-conferencing/office-web-app-server.md)を参照してください。

## <a name="requirements-for-audio-and-video-conferencing"></a>音声ビデオ会議の要件

音声ビデオ会議を計画する場合、組織で必要な種類の会議メディアで求められるネットワーク帯域幅について理解する必要があります。 これには音声、ビデオ、パノラマ ビデオが含まれる可能性があります。 十分なネットワーク帯域幅がない場合、ユーザー エクスペリエンスが大幅に低下する可能性があります。

会議用の音声およびビデオ機能の計画の詳細については、「[Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md)」を参照してください。

通話受付管理 (CAC) を使用して、音声ビデオ会議で使用されるネットワーク帯域幅を管理できます。 これは、中央サイトとブランチ サイト間の帯域幅リンクの制限など、制限のあるネットワークで重要になります。 詳細については、 [Skype のビジネス サーバーでの呼び出しの受付制御の計画](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)を参照してください。

電話会議をネットワークに展開する場合、ユーザーが会議に参加するにはヘッドセットなどのオーディオ デバイスが必要です。 ビデオ会議を展開する場合は、Web カメラなどのビデオ デバイスをユーザー用に展開する必要があります。 オーディオ デバイスまたはビデオ デバイスのいずれの場合も、デバイスの展開とユーザー トレーニングを検討することが重要です。 詳細については、[クライアントとデバイスの計画](../../plan-your-deployment/clients-and-devices/clients-and-devices.md)を参照してください。 最適なユーザー エクスペリエンスを実現するには、Microsoft で認定された統合コミュニケーション (UC) デバイスをすべてのデバイスの種類に使用することをお勧めします。 UC 認定デバイスについての詳細は、[電話や Skype をビジネスのためのデバイス](https://go.microsoft.com/fwlink/?LinkId=619916)を参照してください。

## <a name="requirements-for-dial-in-conferencing"></a>ダイヤルイン会議の要件

ダイヤルイン会議は、さまざまなコンポーネントを含むサーバーのビジネス会議ワークロードの Skype のオプション機能です。 ダイヤルイン会議に固有のコンポーネントの一部と、エンタープライズ VoIP コンポーネントは、いくつか。 このセクションでは、ダイヤルイン会議に必要なコンポーネントの要件について説明します。 仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイの要件に関する詳細については、 [Skype のビジネス サーバー内の仲介サーバー コンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)と[ビジネス サーバーの Skype でトポロジ ビルダーでの仲介サーバーの展開](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)を参照してください。

### <a name="required-components"></a>必要なコンポーネント

ダイヤルイン会議を構成する前に、次の Skype ビジネス サーバー コンポーネントをインストールする必要があります。

- 統合コミュニケーション アプリケーション サービス (UCAS) (アプリケーション サービスと呼ばれます)

- 会議アテンダント アプリケーション

- 会議アナウンス アプリケーション

- ダイヤルイン会議設定 Web ページ

- 少なくとも 1 つの仲介サーバーと少なくとも 1 つの PSTN ゲートウェイ

ダイヤルイン会議、アプリケーション サービス、会議アテンダント アプリケーション、および会議アナウンス アプリケーションのフロント エンド サーバーと同じオペレーティング システムの要件があります。 詳細については、「[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。

会議アテンダント アプリケーションと会議アナウンス アプリケーションは、フロント エンド サーバーに、Windows Media フォーマット ランタイムがインストールされている必要があります。 Windows Media フォーマット ランタイムは、保留音、録音済みの名前、案内で使用される Windows Media オーディオ (WMA) ファイルの再生に必要です。 Windows Server 2012 または Windows Server 2012 R2 (推奨) をインストールする場合は、Windows Media フォーマット ランタイムを取得するのには、Microsoft メディア ファンデーションをインストールする必要があります。 Windows Server 2012 よりも前のバージョンの Windows Server にインストールする場合、Windows Media フォーマット ランタイムを入手するには、Windows デスクトップ エクスペリエンスをインストールしておく必要があります。

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議の音声ファイル要件

ビジネス サーバーの Skype では、ダイヤルイン会議の音声案内や音楽のカスタマイズをサポートしていません。 ただし、既定のオーディオ ファイルを変更する必要がある強力なビジネスの必要性がある場合は、マイクロソフト サポート技術情報 961177、[音声案内や電話会議にダイヤルインの音楽ファイルをカスタマイズする方法](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)を参照してください。

[Microsoft Lync Server 会議アテンダント カスタム音声プロンプトが](https://go.microsoft.com/fwlink/p/?LinkId=396880)管理ユーティリティにより、管理者は電話の呼び出し元が、Skype のカスタム プロンプトの会議に参加するときに使用されるデフォルトの音声プロンプトを置換するのにを使用することもできます。別の会議を提供するエントリが発生します。 カスタム音声プロンプトは、エンタープライズまたは Standard Edition サーバーにインストールできます。

会議アテンダント アプリケーションと会議アナウンス アプリケーション保持、記録されている名前、およびプロンプトのオーディオ ファイルを音楽の次の要件があります。

- Windows Media Audio (WMA) ファイル形式

- 16 ビット モノラル

- 48 Kbps 2-pass CBR (固定ビット レート)

- -24DB の音声レベル

### <a name="user-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のユーザー要件

ダイヤルイン会議ユーザーは、そのアカウントに固有の電話番号または内線番号を割り当てておく必要があります。 この要件によりダイヤルイン会議中の認証が可能になります。 エンタープライズ ユーザー (つまり、組織内でのビジネスのサーバー アカウントを Active Directory ドメイン サービスの資格情報と Skype を持っている)、電話番号 (または拡張子) を入力し、暗証番号 (PIN) として会議にダイヤルインするには認証済みユーザーです。

## <a name="port-requirements-for-conferencing"></a>会議のポート要件

ビジネス サーバーの Skype では、会議機能を使用するには、特定のポートが開かれていることが必要です。 次の表に、会議のポート要件の一覧を示します。 すべてのポート要件の詳細については、[サーバーのポートとプロトコルの要件](../../plan-your-deployment/network-requirements/ports-and-protocols.md)を参照してください。

**必要なサーバー ポート**


|**サーバーの役割**|**サービス名**|**ポート**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|:-----|:-----|
|フロントエンド サーバー  <br/> |ビジネス Server IM 会議サービスの Skype  <br/> |5062  <br/> |TCP  <br/> |インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |ビジネス サーバーの Web 会議サービスの Skype  <br/> |8057  <br/> |TCP (TLS)  <br/> |クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype ビジネス サーバーの Web 会議の互換性のサービスの  <br/> |8058  <br/> |TCP (TLS)  <br/> |永続共有オブジェクト モデル (PSOM) からの接続、Live Meeting クライアントと以前のバージョンの Skype ビジネス サーバーのリッスンに使用されます。  <br/> |
|フロントエンド サーバー  <br/> |ビジネス サーバー オーディオ/ビデオ会議サービスの Skype  <br/> |5063  <br/> |TCP  <br/> |音声ビデオ会議の SIP 要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |ビジネス サーバー オーディオ/ビデオ会議サービスの Skype  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |ビデオ会議で使用するメディア ポート範囲。  <br/> |
|フロントエンド サーバー  <br/> |Skype ビジネス Server 会議アテンダント サービス (ダイヤルイン会議) の  <br/> |5064  <br/> |TCP  <br/> |ダイヤルイン会議の SIP 要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |Skype ビジネス Server 会議アテンダント サービス (ダイヤルイン会議) の  <br/> |5072  <br/> |TCP  <br/> |アテンダント (ダイヤルイン会議) の受信 SIP 要求を使用します。  <br/> |
|フロントエンド サーバー  <br/> |ビジネス サーバー アプリケーションの共有サービスの Skype  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロントエンド サーバー  <br/> |ビジネス サーバー アプリケーションの共有サービスの Skype  <br/> |49152-65535  <br/> |TCP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
|フロントエンド サーバー  <br/> |ビジネス サーバー会議アナウンス サービスの Skype  <br/> |5073  <br/> |TCP  <br/> |ビジネス サーバー会議アナウンス サービスの Skype の着信 SIP 要求を使用する (つまり、ダイヤルイン会議のため)。  <br/> |
|すべての内部サーバー  <br/> |各種  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用される: フロント エンド サーバー (ビジネス Server 会議アテンダント サービスの Skype、ビジネス サーバー会議アナウンス サービスでは、Skype と Skype ビジネス サーバー オーディオ/ビデオ会議サービス用) と仲介サーバー。  <br/> |
|Office Web Apps サーバー  <br/> ||443  <br/> ||Office Web アプリケーション サーバーに接続するのには、Skype のビジネス サーバーによって使用されます。  <br/> |

**必要なクライアント ポート**


|**ポート**|**プロトコル**|**メモ**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Web 会議セッションへの外部ユーザー アクセスで使用  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |音声ビデオ セッションとメディアへの外部ユーザー アクセス (UDP) で使用。  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |オーディオ ポート範囲 (少なくとも 20 個のポートが必要)。  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |ビデオ ポート範囲 (少なくとも 20 個のポートが必要)。  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |アプリケーション共有  <br/> |


