---
title: 仮想アクセスのチーム
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams を使用して仮想ビジットシステムをセットアップする
ms.openlocfilehash: 3d5d68e7c4ba3cc203df33604a7210e67b402938
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778890"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>チームでの仮想アクセス-EHR との統合

Microsoft Teams の電子医療記録 (EHR) コネクタを使用すると、clinicians は、EHR システムから直接、Teams の他のプロバイダーとの間で仮想患者のアクセスや相談を簡単に開始できます。 Microsoft Teams では、microsoft 365 クラウドを基盤として、Microsoft Teams を使用することで、HIPAA、ビデオ、音声、および医療ツールとのシンプルで安全な共同作業とコミュニケーションが実現されます。これは、HIPAA への準拠をサポートしている単一のハブです。

チームのコミュニケーションとコラボレーションのプラットフォームにより、clinicians は、断片化されたシステムの低優先メールを簡単にカットできるため、時間を節約できます。 Microsoft Teams の電子医療記録 (EHR) コネクタは、次のことができます。

- プロバイダーと患者の両方のポータルから、Teams の仮想アクセスを起動します。

- 自動監査とレコード保持を有効にするには、接続イベントと切断イベントに関する EHR メタデータに書き戻します。

- 既存の clinician と患者のワークフローに統合しながら、Microsoft Teams を使用できるようにします。

  EHR ポータルから仮想アクセスを管理する方法のビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>始める前に

EHR コネクタを統合するには、次の前提条件が満たされていることを確認する必要があります。

- 医療機関向けの Microsoft Cloud、または Microsoft Teams の EHR コネクタスタンドアロンサービスのサブスクリプション。

- ユーザーには、Microsoft Teams の会議を含む適切な Microsoft 365 または Office 365 のライセンスが必要です。

- Microsoft Teams は、組織内で採用して使用する必要があります。

- 組織には、2018年11月以降のエピックバージョンが必要です。

- システムは、 [ソフトウェアとブラウザーのすべての前提条件を](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)満たしている必要があります。

組織内の次のユーザーからの情報も必要になります。

- Microsoft 365 管理者

- エピック管理者

> [!Note]
> エピック管理者に依頼して、エピック市場で利用可能な Epic-Microsoft Teams のテレライフの統合ガイドを提供してください。

## <a name="connector-setup"></a>コネクタのセットアップ

コネクタのセットアップでは、次のことを行う必要があります。

- [EHR コネクタ構成ポータルを起動する](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [プロバイダー組織の情報を構成する](ehr-admin.md#configure-provider-organization-information)
- [構成を確認して承認する](ehr-admin.md#verify-and-approve-the-configuration)
- [構成を確認して完了する](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[EHR コネクタ構成ポータルを起動する](#launch-the-ehr-connector-configuration-portal)

Microsoft Teams で仮想アクセスを起動するように医療組織を構成するには、EHR コネクタ構成ポータルを起動します。 テスト URL を使って、エピックテスト環境のコネクタを構成します。 エピックの運用環境を有効にする準備ができたら、プロダクション URL を使います。
  
- テスト環境 [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)
- 運用環境 [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

組織の Microsoft 365 管理者とエピックの管理者は、構成ポータルで情報と統合の手順を完了する必要があります。 エピック構成手順については、組織に割り当てられているエピックリソースに問い合わせてください。

### <a name="configure-provider-organization-information"></a>[プロバイダー組織の情報を構成する](#configure-provider-organization-information)

この手順は、Microsoft 365 管理者によって完了されます。 Microsoft 365 管理者は、コネクタ構成ポータルを起動し、Microsoft 資格情報でサインインして、構成プロセスを開始する必要があります。

この手順を完了するために、Microsoft 365 管理者は、Microsoft 365 管理者から、構成を承認するエピック管理者のユーザー名から、有効な Fast Health の相互運用性リソース (FHIR) ベース URL を受け取る必要があります。 Microsoft 365 管理者は、コネクタ構成ページを起動し、Microsoft 資格情報でサインインして、構成プロセスを開始する必要があります。

- FHIR ベース URL は、サーバー FHIR API エンドポイントに対応する静的アドレスです。 URL の例を次に示し [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) ます。

- 構成承認者名は、構成の承認を担当するエピックシステム管理者の名前です。

  ![構成承認者名は、EHR コネクタのリストから選択されます。](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[構成を確認して承認する](#verify-and-approve-the-configuration)

承認者として追加された医療機関向けのエピック管理者は、前の手順と同じ EHR コネクタ URL を使用して、Microsoft 365 の資格情報を使ってサインインする必要があります。 検証に成功した後、承認者はエピックの資格情報を使用して、エピック組織を検証するように求められます。

> [!Note]
> 組織内の Microsoft 365 管理者とエピックの管理者は、同じユーザーになることができます。 その場合は、最初の手順で承認者として独自のユーザー名を追加します。 引き続き、エピックにサインインして、アクセスを検証する必要があります。 エピックのサインインは、FHIR のベース URL を検証するためだけに使用されます。 Microsoft は、このサインインを使用して、資格情報を保存したり、EHR データにアクセスしたりすることはありません。

  ![資格情報の構成を確認し、承認します。](../../media/ehc-provider-2.png)

成功したエピックにサインインすると、エピック管理者が構成を承認 **する必要があり** ます。 構成が正しくない場合、Microsoft 365 管理者は、Microsoft EHR コネクタポータルにもう一度サインインして、元の構成を変更することができます。

![EHR コネクタが構成されていることを確認し、構成を変更するオプションを選択します。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[構成を確認して完了する](#review-and-finish-the-configuration)

構成情報がエピック管理者によって承認されると、患者とプロバイダーの起動のための統合レコードが表示されます。 これらのレコードは、エピックで仮想アクセス構成を完了するために必要です。 詳細については、Epic-Microsoft Teams の「テレライフの統合」を参照してください。

> [!Note]  
> いつでも、Microsoft 365 またはエピックの管理者は、構成ポータルにサインインして、統合レコードを表示し、必要に応じて組織の構成を変更することができます。

![統合情報が表示されます。](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a>チームの仮想訪問を開始する

EHR コネクタの手順とエピックの構成を完了すると、組織で Microsoft Teams を使用してビデオ通話をサポートできるようになります。

### <a name="virtual-visit-prerequisites"></a>仮想アクセスの前提条件

- システムは、 [ソフトウェアとブラウザーのすべての前提条件を](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)満たしている必要があります。

- 医療機関は、エピック組織と Microsoft 365 組織間のセットアップを完了する必要があります。

### <a name="provider-experience"></a>プロバイダーの操作

組織の医療機関は、エピックプロバイダアプリケーション (ハイパースペース、Haiku、Canto) から Microsoft Teams を使用して仮想訪問に参加することもできます。 [ **仮想アクセスの開始** ] ボタンがプロバイダーフローに埋め込まれます。

プロバイダーエクスペリエンスの主な機能:

- プロバイダーは、サポートされているブラウザーまたは Microsoft Teams アプリケーションを使用して仮想ビジットに参加できます。

- プロバイダーは、仮想訪問を初めて参加するときに、Microsoft 365 アカウントで1回サインインする必要があります。

- 一度サインインすると、プロバイダーは Microsoft Teams の仮想予定に直接取り込まれます。 (プロバイダーは Microsoft Teams にサインインしている必要があります)。

- プロバイダーは、特定の予定について、参加者の接続と切断をリアルタイムで行うことができます。 プロバイダーは、患者が仮想アクセスに接続されているかどうかを確認できます。

  ![患者との仮想アクセスのプロバイダーエクスペリエンス](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>患者の体験

コネクタは、MyChart の web およびモバイルを通じて仮想訪問に参加する患者をサポートします。 予定の時点では、患者は [ **仮想アクセスの開始** ] ボタンを使って、MyChart から仮想アクセスを開始できます。

患者の体験の主要機能:

- 患者は、アプリがインストールされていなくても、デスクトップおよびモバイルの最新の web ブラウザーから仮想アクセスに参加できます。

- 患者は1回のクリックで仮想訪問に参加できます。追加のアカウントがないか、サインインする必要がありません。

- 患者は、Microsoft アカウントを作成したり、サインインして仮想アクセスを開始したりする必要はありません。

- 患者は、医療機関がその予定に参加して、仮想アクセスを許可するまで、ロビーに配置されます。

- ビデオとマイクのテストは、仮想アクセスの参加前にロビーで行うことができます。

  ![仮想アクセスの患者の体験](../../media/ehc-virtual-visit-5.png)

> [!Note]
> エピック、MyChart、Haiku、および Canto、エピックシステム Corporation の商標です。

### <a name="privacy-and-location-of-data"></a>データのプライバシーと場所

チームと EHR システムの統合により、統合および仮想アクセスフローで使用されるデータ量が最適化されます。 このソリューションは、チームのプライバシーに関する全体的なチームのプライバシーとデータ管理の原則とガイドラインに従っています。

Microsoft Teams EHR コネクタは、EHR システムから特定の個人データ、または患者や医療機関の健康記録を保存することはできません。 EHR コネクタによって保存されるデータは、EHR ユーザーの固有の ID です。これは、Teams の会議のセットアップ時に使用されます。 EHR ユーザーの固有の ID は、「 [Microsoft 365 顧客データの保存場所](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) 」で説明されている3つの地理的な地域のいずれかに保存されています。 会議の参加者によってチームに入力されたすべてのチャット、レコーディング、その他のデータは、既存のストレージポリシーに従って保存されます。 Microsoft Teams のデータの場所について詳しく知りたい場合は、Teams の [データの場所](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)を参照してください。
