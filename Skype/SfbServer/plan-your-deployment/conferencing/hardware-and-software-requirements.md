---
title: Skype for Business Server での会議のハードウェアとソフトウェアの要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: '概要: このトピックでは、Skype for Business Server での会議のハードウェア要件とソフトウェア要件について説明します。'
ms.openlocfilehash: 6ffa86266d8782e9e49c708998714bef4dbbed51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118516"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Skype for Business Server での会議のハードウェアとソフトウェアの要件

**概要:** このトピックでは、Skype for Business Server での会議のハードウェア要件とソフトウェア要件について説明します。

このセクションでは、Web 会議、音声ビデオ (A/V) 会議、ダイヤルイン会議、インスタント メッセージング (IM) 会議のハードウェア要件とソフトウェア要件について説明します。 すべての会議機能は、フロント エンド サーバーで実行されます。次の図に示すように、さまざまな種類の会議に関する追加の要件があります。

たとえば、ダイヤルイン会議を許可する場合は、仲介サーバーと公衆交換電話網 (PSTN) に接続するためのゲートウェイを展開する必要があります。 Web 会議を許可する場合は、Skype for Business Server が Web Apps サーバーに接続Office必要があります。 外部ユーザーに会議への参加を許可する場合は、エッジ サーバーを展開する必要があります。

**会議の機能と要件**

![会議コンポーネント](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 トポロジに関する考慮事項の詳細については、「Skype for Business Server の会議トポロジを計画 [する」を参照してください](conferencing-topology.md)。

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>フロントエンド サーバーのハードウェア要件とソフトウェア要件

Web 会議、音声ビデオ会議、ダイヤルイン会議、IM 会議はすべてフロント エンド サーバーに関連付けられたため、サーバーのハードウェア要件とソフトウェア要件はフロント エンド サーバーの要件と同じです。 これらの要件の詳細については [、「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) のサーバー要件」および [「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) の環境要件」または [「Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)のサーバー要件」を参照してください。

## <a name="requirements-for-web-conferencing"></a>Web 会議の要件

Web 会議を有効にすることにした場合、次のものを計画する必要があります。

- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。

- 会議中Office PowerPoint ファイルを共有するために必要な Web Apps Server との統合。

### <a name="file-store"></a>ファイル ストア

Skype for Business Server Web 会議サービスは、会議中に共有されるコンテンツをファイル ストアに保存します。 展開の一環として、Standard Edition サーバーまたは Enterprise Edition フロントエンド プールのファイル ストアとして使用するファイル共有を指定する必要があります。 ファイル ストアに既存のファイル共有を使用するか、ファイル共有を保存するファイル サーバーの完全修飾ドメイン名 (FQDN) と、新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定できます。 詳細については [、「Create a file share in Skype for Business Server」を参照してください](../../deploy/install/create-a-file-share.md)。 Web 会議サービスは、コンテンツをファイル ストアに格納する前にコンテンツを暗号化します。

Skype for Business Server では、直接接続ストレージ (DAS) または記憶域ネットワーク (SAN) (分散ファイル システム (DFS) を含む) でのファイル共有の使用と、ファイル ストア用の独立ディスク (RAID) の冗長アレイでのファイル共有の使用がサポートされています。 Skype for Business Server 展開ウィザードでファイル共有の場所が定義された後、Skype for Business Server は次のようなファイル共有内にフォルダー構造を作成します。

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。

### <a name="office-web-apps-server"></a>Office Web Apps サーバー

Web 会議機能を使用するには、Web Apps サーバー Officeインストールし、Skype for Business Server が Web Apps サーバーと通信Officeする必要があります。

Office Web Apps Server は、Skype for Business Server、SQL Server、または他のサーバー アプリケーションを実行していないスタンドアロン コンピューターにインストールする必要があります。 (そのコンピューターにインストールされているバージョンOffice必要があります)。Web Apps Server の実行にOfficeコンピューターには、特定のソフトウェア セット (.NET Framework 4.5 および Windows PowerShell 3.0 を含む) がインストールされている必要があります。 これらの要件は、証明書とインターネット インフォメーション サービス (IIS) の構成に関する情報と共に、web Apps 展開 web サイトの Microsoft Office [で詳しく説明されています](/webappsserver/deploy-the-infrastructure-office-web-apps-server)。

Skype for Business Server が Office Web Apps サーバーと連携する構成方法については、「Configure integration with Office Web Apps [Server in Skype for Business Server」を参照してください](../../deploy/deploy-conferencing/office-web-app-server.md)。

## <a name="requirements-for-audio-and-video-conferencing"></a>電話会議およびビデオ会議の要件

音声ビデオ会議を計画する場合、組織で必要な種類の会議メディアで求められるネットワーク帯域幅について理解する必要があります。 これには、オーディオ、ビデオ、パノラマ ビデオが含まれます。 十分なネットワーク帯域幅がない場合、ユーザー エクスペリエンスが著しく低下する可能性があります。

電話会議のオーディオとビデオの容量計画の詳細については、「Skype for Business のネットワーク要件を [計画する」を参照してください](../../plan-your-deployment/network-requirements/network-requirements.md)。

通話受付管理 (CAC) を使用して、音声ビデオ会議で使用されるネットワーク帯域幅を管理できます。 これは、中央サイトとブランチ サイト間の制限された帯域幅リンクなど、制限されたネットワークにとって重要です。 詳細については [、「Plan for call admission control in Skype for Business Server」を参照してください](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。

ネットワークに電話会議を展開する場合、ユーザーは電話会議に参加するためにヘッドセットなどのオーディオ デバイスが必要になります。 ビデオ会議を展開する場合は、ユーザー用の Web カメラなどのビデオ デバイスを展開する必要があります。 オーディオ デバイスとビデオ デバイスの両方にとって、デバイスの展開とユーザー トレーニングは考慮すべき重要な手順です。 詳細については、「Plan [for clients and devices」を参照してください](../../plan-your-deployment/clients-and-devices/clients-and-devices.md)。 Microsoft では、最適なユーザー エクスペリエンスを実現するために、すべてのデバイスの種類について Microsoft によって認定されているユニファイド コミュニケーション (UC) デバイスを使用してください。 UC 認定デバイスの詳細については [、「Phones and devices for Skype for Business」を参照してください](../../../SfbPartnerCertification/certification/devices-ip-phones.md)。

## <a name="requirements-for-dial-in-conferencing"></a>ダイヤルイン会議の要件

ダイヤルイン会議は、さまざまなコンポーネントを含む Skype for Business Server 会議ワークロードのオプション機能です。 コンポーネントの中には、ダイヤルイン会議固有のものも、エンタープライズ VoIP コンポーネントもあります。 このセクションでは、ダイヤルイン会議に必要なコンポーネントの要件について説明します。 仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイ要件の詳細については [、「Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) の仲介サーバー コンポーネント」および [「Skype](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)for Business Server のトポロジ ビルダーでの仲介サーバーの展開」を参照してください。

### <a name="required-components"></a>必須コンポーネント

ダイヤルイン会議を構成する前に、次の Skype for Business Server コンポーネントをインストールする必要があります。

- 統合コミュニケーション アプリケーション サービス (UCAS) (アプリケーション サービスと呼ばれます)

- 会議アテンダント アプリケーション

- 会議アナウンス アプリケーション

- ダイヤルイン会議設定 Web ページ

- 少なくとも 1 つの仲介サーバーと少なくとも 1 つの PSTN ゲートウェイ

ダイヤルイン会議の場合、Application Service、会議アテンダント アプリケーション、および会議アナウンス アプリケーションには、フロント エンド サーバーと同じオペレーティング システム要件があります。 詳細については [、「Skype for Business Server 2015 のサーバー](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)要件」を参照してください。

会議アテンダント アプリケーションと会議アナウンス アプリケーションでは、Windows Media Format Runtime がフロントエンド サーバーにインストールされている必要があります。 保留音、録音名、およびプロンプトに使用される Windows Media オーディオ (WMA) ファイルを再生するには、Windows Media Format ランタイムが必要です。 Windows Server 2012 または Windows Server 2012 R2 にインストールする場合 (推奨)、Windows Media Format ランタイムを取得するには、Microsoft Media Foundation をインストールする必要があります。 Windows 2012 より前のバージョンの Windows Server にインストールする場合は、Windows Media Format Runtime を取得するために Windows デスクトップ エクスペリエンスがインストールされていることを確認する必要があります。

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議の音声ファイル要件

Skype for Business Server では、ダイヤルイン会議用の音声プロンプトと音楽のカスタマイズはサポートされていません。 ただし、既定のオーディオ ファイルを変更する必要がある強力なビジネスニーズがある場合は、Microsoft サポート技術情報の記事 961177、「ダイヤルイン電話会議用に音声プロンプトまたは音楽ファイルをカスタマイズする方法」を参照してください。 [](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)

[また、Microsoft Lync Server 会議](https://go.microsoft.com/fwlink/p/?LinkId=396880)アテンダント カスタム音声プロンプト管理ユーティリティを使用することもできます。これにより、管理者は、電話発信者が Skype for Business 会議に参加するときに使用される既定の音声プロンプトをカスタム プロンプトに置き換え、別の会議エントリ エクスペリエンスを提供できます。 カスタム音声プロンプトは、エンタープライズ サーバーまたは Standard Edition サーバーにインストールできます。

会議アテンダント アプリケーションと会議アナウンス アプリケーションには、保留音、録音名、および音声プロンプト ファイルに関する次の要件があります。

- Windows Media Audio (WMA) ファイル形式

- 16 ビット モノラル

- 48 Kbps 2-pass CBR (固定ビット レート)

- -24DB の音声レベル

### <a name="user-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のユーザー要件

ダイヤルイン会議ユーザーは、そのアカウントに固有の電話番号または内線番号を割り当てておく必要があります。 この要件によりダイヤルイン会議中の認証が可能になります。 エンタープライズ ユーザー (つまり、組織内の Active Directory ドメイン サービス資格情報と Skype for Business Server アカウントを持つユーザー) は、認証されたユーザーとして電話会議にダイヤルインする電話番号 (または内線番号) と個人識別番号 (PIN) を入力します。

## <a name="port-requirements-for-conferencing"></a>会議のポート要件

会議機能を使用するには、Skype for Business Server では、特定のポートが開いている必要があります。 次の表に、会議のポート要件を示します。 すべてのポート要件の詳細については、「サーバーの [ポートとプロトコルの要件」を参照してください](../../plan-your-deployment/network-requirements/ports-and-protocols.md)。

**必要なサーバー ポート**


|**サーバーの役割**|**サービス名**|**Port**|**プロトコル**|**注**|
|:-----|:-----|:-----|:-----|:-----|
|フロント エンド サーバー  <br/> |Skype for Business Server IM 会議サービス  <br/> |5062  <br/> |TCP  <br/> |インスタント メッセージング (IM) 会議の SIP 要求を受信するために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server Web 会議サービス  <br/> |8057  <br/> |TCP (TLS)  <br/> |クライアントからの PSOM (永続共有オブジェクト モデル) 接続をリッスンするために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server Web 会議の互換性サービス  <br/> |8058  <br/> |TCP (TLS)  <br/> |Live Meeting クライアントと以前のバージョンの Skype for Business Server から永続的な共有オブジェクト モデル (PSOM) 接続をリッスンするために使用されます。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server 音声ビデオ会議サービス  <br/> |5063  <br/> |TCP  <br/> |音声ビデオ会議の SIP 要求を受信するために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server 音声ビデオ会議サービス  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |ビデオ会議で使用するメディア ポート範囲。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server 会議アテンダント サービス (ダイヤルイン会議)  <br/> |5064  <br/> |TCP  <br/> |ダイヤルイン会議の SIP 要求を受信するために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server 会議アテンダント サービス (ダイヤルイン会議)  <br/> |5072  <br/> |TCP  <br/> |応答 (ダイヤルイン会議) の着信 SIP 要求に使用されます。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |5065  <br/> |TCP  <br/> |アプリケーション共有の SIP リッスン要求を受信するために使用。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server アプリケーション共有サービス  <br/> |49152-65535  <br/> |TCP  <br/> |アプリケーション共有で使用するメディア ポート範囲。  <br/> |
|フロント エンド サーバー  <br/> |Skype for Business Server 会議アナウンス サービス  <br/> |5073  <br/> |TCP  <br/> |Skype for Business Server 会議アナウンス サービス (つまり、ダイヤルイン会議用) の受信 SIP 要求に使用されます。  <br/> |
|すべての内部サーバー  <br/> |各種  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |すべての内部サーバーでのオーディオ会議で使用するメディア ポート範囲。 オーディオを終了するすべてのサーバーで使用されます。フロントエンド サーバー (Skype for Business Server 会議アテンダント サービス、Skype for Business Server 会議アナウンス サービス、Skype for Business Server オーディオ/ビデオ会議サービス)、仲介サーバー。  <br/> |
|Office Web Apps サーバー  <br/> ||443  <br/> ||Skype for Business Server が Web Apps サーバーに接続Office使用します。  <br/> |

**必要なクライアント ポート**


|**Port**|**プロトコル**|**注**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Web 会議セッションへの外部ユーザー アクセスで使用。  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |音声ビデオ セッションとメディアへの外部ユーザー アクセス (TCP) で使用  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |A/V セッションおよびメディア (UDP) への外部ユーザー アクセスに使用されます。  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |オーディオ ポート範囲 (少なくとも 20 個のポートが必要)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |ビデオ ポート範囲 (少なくとも 20 個のポートが必要)  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |アプリケーション共有。  <br/> |