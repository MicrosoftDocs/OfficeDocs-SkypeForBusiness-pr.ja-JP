---
title: Teams for Virtual の訪問
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams を使用して仮想訪問システムをセットアップする
ms.openlocfilehash: 6753afbabf6bbcb420f9ddf479249a968d33eb2c
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055716"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Teams を使用した仮想アクセス - EHR への統合

Microsoft Teams 電子健康記録 (EHR) コネクタを使用すると、診療所は、EHR システムから直接 Teams で仮想患者訪問または別のプロバイダーとの相談を簡単に開始できます。 Microsoft Teams は、Microsoft 365 クラウド上に構築され、HIPAA、HITECH 認定、その他のコンプライアンスをサポートする単一のハブで、チャット、ビデオ、音声、医療ツールを使用した簡単で安全な共同作業とコミュニケーションを可能にしています。
Teams のコミュニケーションプラットフォームとコラボレーション プラットフォームを使用すると、診療所は断片化したシステムを簡単に切り取り、可能な限り最適なケアを提供するために時間を費やします。 Microsoft Teams 電子健康記録 (EHR) コネクタでは、次の機能を使用できます。
- Teams の仮想アクセスをプロバイダーポータルと患者ポータルの両方から起動します。
- 接続イベントと切断イベントの EHR メタデータに書き戻して、自動監査と記録の保持を有効にする。
- Microsoft Teams を使用しながら、既存の診療所や患者のワークフローに統合します。

  EHR ポータルから仮想アクセスを管理する方法のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>開始する前に

EHR コネクタを統合する前に、次の前提条件を満たしていることを確認する必要があります。

- エピスの App Marketplace マーケットプレースで Microsoft Teams [アプリに使用するアクセス](https://apporchard.epic.com/Gallery?id=6153)。

- 医療向け Microsoft Cloud のアクティブなサブスクリプション、または Microsoft Teams EHR Connector 単体プランのサブスクリプション。

- ユーザーは、Microsoft Teams 会議を含む適切な Microsoft 365 Office 365 ライセンスを持っている必要があります。

- Microsoft Teams は組織内で採用および使用する必要があります。

- 組織は、2018 年 11 月以降のバージョンのエピスを使用している必要があります。

- システムは、すべてのソフトウェアと [ブラウザーの前提条件を満たす必要があります](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。

組織内の次のユーザーからの情報も必要です。

- Microsoft 365 管理者

- 壮大な顧客アナリスト

> [!Note]
> 壮大なテクニカル スペシャリストに依頼して、エEpic-Microsoftマーケットプレースで利用可能な Teams Telehealth Integration Guide の機能を提供してください。

## <a name="connector-setup"></a>コネクタのセットアップ

コネクタのセットアップでは、次の操作を行う必要があります。

- [EHR コネクタ構成ポータルを起動する](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [構成情報](ehr-admin.md#configuration-information)
- [構成を承認または表示する](ehr-admin.md#approve-or-view-configuration)
- [構成を確認して完了する](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[EHR コネクタ構成ポータルを起動する](#launch-the-ehr-connector-configuration-portal)

Microsoft Teams で仮想アクセスを開始するための医療組織の構成は、EHR Connector 構成ポータルを起動して開始します。 統合をテストするために、1 つ以上の組織を構成します。 構成ポータルでテストと実稼働の URL を構成します。 実稼働環境に移行する前に、エピスのテスト環境から統合をテストします。
  
- EHR コネクタ構成 URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

組織の Microsoft 365 管理者および壮大な顧客アナリストは、構成ポータルの情報と統合の手順を完了する必要があります。 壮大な構成手順については、組織に割り当てられているエピスの技術専門リソースにお問い合わせください。

### <a name="configuration-information"></a>[構成情報](#configuration-information)

この手順は **、Microsoft 365 管理者が行います**。 Microsoft 365 管理者が構成プロセスを開始するには、コネクタ構成ポータルを起動し、Microsoft 資格情報でサインインする必要があります。

この手順を完了するには、Microsoft 365 管理者が、有効なファースト Health 相互運用性リソース (FHIR) ベース URL を、エピスの技術専門家と、構成を承認するエピスの顧客アナリストのユーザー名を受け取る必要があります。 Microsoft 365 管理者は、コネクタ構成ページを起動し、Microsoft 資格情報でサインインして構成プロセスを開始する必要があります。

- FHIR ベース URL は、サーバー FHIR API エンドポイントに対応する静的アドレスです。 URL の例 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` は次のようになります。

- 構成承認者の名前は、次の手順で構成の承認を担当する、壮大な顧客アナリストの名前です。 壮大な顧客アナリストは、組織のユーザーで、エピスへのサインイン アクセス権を持っています。

  ![構成承認者の名前は、EHR コネクタの一覧から選択されます。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[構成を承認または表示する](#approve-or-view-configuration)

承認者として追加された医療組織の壮大な顧客アナリストは、Microsoft 365 の資格情報を使用してサインインするために、前の手順と同じ EHR Connector URL を使用する必要があります。 検証が成功した後、承認者は、エピカル組織を検証するために、エピカルの資格情報を使用してサインインを求めるメッセージが表示されます。

> [!Note]
> 組織内の Microsoft 365 管理者とエピスの顧客アナリストは、同じ人物である可能性があります。 その場合は、独自のユーザー名を承認者として追加します。 アクセスを検証するには、引き続きエピスにサインインする必要があります。 エピカル サインインは、FHIR ベース URL の検証にのみ使用されます。 Microsoft は、このサインインで資格情報を保存したり、EHR データにアクセスしたりは行ないます。

  ![資格情報の構成を確認して承認します。](../../media/approve-view-configuration.png)

エピスのサインインが成功した後、壮大な顧客アナリストが **構成を** 承認する必要があります。 構成が正しく設定されていない場合、Microsoft 365 管理者は、Microsoft EHR コネクタ ポータルにもう一度サインインして、元の構成を変更できます。 

![EHR コネクタが構成されていることを確認し、構成を変更するオプションを選択します。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[構成を確認して完了する](#review-and-finish-the-configuration)

構成情報が壮大な管理者によって承認されると、患者とプロバイダーの立ち上げに関する統合レコードが表示されます。 これらのレコードは、壮大な仮想訪問構成を完了するために必要です。 詳細については、Epic-Microsoft Teams Telehealth Integration ガイドを参照してください。

> [!Note]  
> Microsoft 365 または壮大な顧客アナリストは、いつでも構成ポータルにサインインして統合レコードを表示し、必要に応じて組織の構成を変更できます。

![統合情報が表示されます。](../../media/finish-configuration.png)

> [!Note]
> 承認プロセスは、以前に Microsoft 管理者によって構成された FHIR URL ごとに、壮大な顧客アナリストによって完了する必要があります。

![構成情報が承認されます。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Teams の仮想アクセスを開始する

EHR Connector の手順と壮大な構成が完了すると、組織は Microsoft Teams でのビデオアクセスをサポートする準備が整います。

### <a name="virtual-visit-prerequisites"></a>仮想アクセスの前提条件

- システムは、すべてのソフトウェアと [ブラウザーの前提条件を満たす必要があります](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。

- 医療組織は、エピスの組織と Microsoft 365 組織の間のセットアップを完了している必要があります。

### <a name="provider-experience"></a>プロバイダーエクスペリエンス

組織の医療プロバイダーは、壮大なプロバイダー アプリケーション (Hyperspace、Haグループ、Canto) から Microsoft Teams を使用して仮想訪問に参加することもできます。 [ **仮想アクセスの開始]** ボタンがプロバイダー フローに埋め込まれている。

プロバイダーエクスペリエンスの主な機能:

- プロバイダーは、サポートされているブラウザーまたは Microsoft Teams アプリケーションを使用して仮想アクセスに参加できます。

- プロバイダーは、仮想アクセスに初めて参加する際に、Microsoft 365 アカウントで 1 回のサインインを行う必要があります。

- 1 回のサインイン後、プロバイダーは Microsoft Teams の仮想予定に直行されます。 (プロバイダーは Microsoft Teams にサインインしている必要があります)。

- プロバイダーは、特定の予定に対する参加者の接続と切断のリアルタイムの更新を表示できます。 プロバイダーは、患者がいつ仮想訪問に接続されたのか確認できます。

  ![患者との仮想訪問のプロバイダーエクスペリエンス](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>患者の経験

このコネクタは、MyChart Web とモバイルを介して仮想訪問に参加する患者をサポートします。 予約の時点で、患者は [仮想訪問の開始] ボタンを使用して、MyChart から **仮想訪問を開始** できます。

患者の経験の主な機能:

- 患者は、アプリをインストールすることなく、デスクトップとモバイルの最新の Web ブラウザーから仮想アクセスに参加できます。

- 患者は 1 回のクリックで仮想訪問に参加できます。他のアカウントやサインインは必要ありません。

- 患者は、Microsoft アカウントを作成したり、仮想アクセスを開始するためにサインインしたりする必要はありません。

- 患者は、医療プロバイダーが予定に参加し、仮想訪問を認めるまでロビーに置かれる予定です。

- 仮想アクセスに参加する前に、ロビーでビデオとマイクのテストを利用できます。

  ![仮想訪問の患者体験](../../media/ehc-virtual-visit-5.png)

> [!Note]
> エピクト、MyChart、Ha、Canto は、エピクト システム社の商標です。

### <a name="privacy-and-location-of-data"></a>データのプライバシーと場所

Teams を EHR システムに統合すると、統合中に使用および保存されるデータの量と仮想訪問フローが最適化されます。 このソリューションは、Teams のプライバシーとデータ管理に関する全体的な原則と、Teams のプライバシーに関するガイドラインに従います。

Microsoft Teams EHR コネクタは、識別可能な個人データや、患者や医療プロバイダーの医療記録を EHR システムから保存または転送しない。 EHR コネクタによって保存される唯一のデータは、Teams 会議のセットアップ中に使用される EHR ユーザーの一意の ID です。 EHR ユーザーの一意の ID は [、Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)の顧客データが保存される場所で説明されている 3 つの地理的領域の 1 つに格納されます。 会議の参加者によって Teams に入力されたチャット、レコーディング、その他のデータはすべて、既存のストレージ ポリシーに従って保存されます。 Microsoft Teams のデータの場所の詳細については、「Teams のデータの場所 [」を参照してください](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)。
