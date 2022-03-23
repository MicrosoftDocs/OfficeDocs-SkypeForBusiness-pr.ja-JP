---
title: 仮想アクセスと Teams - Cerner EHR への統合
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Teams EHR コネクタを統合して、組織内の医療プロバイダーが Cerner EHR システムから直接 Teams で患者または他のプロバイダーと仮想訪問を行う方法について説明します。
ms.openlocfilehash: 6c0f0020cbbee5ba6ecbb186681454b8d8b8a103
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711751"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>仮想アクセスと Teams - Cerner EHR への統合

Microsoft Teams電子健康記録 (EHR) コネクタを使用すると、医師は、Cerner EHR システムから直接、Microsoft Teams で仮想患者訪問を開始したり、別のプロバイダーと相談したりすることができます。 Microsoft 365 クラウド上に構築された Teams は、HIPAA、HITECH 認定などへの準拠をサポートする単一のハブで、チャット、ビデオ、音声、および医療ツールとの簡単で安全なコラボレーションと通信を可能にしています。

Teams のコミュニケーションおよびコラボレーション プラットフォームを使用すると、クリニアンは断片化されたシステムの煩雑な部分を簡単に切り取り、可能な限り最善のケアの提供に集中できます。 EHR コネクタTeams使用すると、次の方法を実行できます。

- 統合Teamsワークフローを使用して、Cerner EHR システムから仮想訪問を実施します。
- 患者が電子メールまたは SMS 通知Teams仮想アクセスに参加できます。
- EHR に接続された訪問の消費データ レポートとカスタマイズ可能な通話品質情報を表示します。

この記事では、Cerner プラットフォームと統合Teams EHR コネクタを設定および構成する方法について説明します。 また、Cerner EHR システムTeams Virtual Visits エクスペリエンスの概要も示します。

## <a name="before-you-begin"></a>はじめに

> [!NOTE]
> 統合を有効にする前に、必ず Cerner の担当者に相談し、Cerner 統合ガイドを確認してください。

### <a name="prerequisites"></a>前提条件

医療組織で Teams EHR コネクタを統合する前に、次の情報が必要です。

- EHR コネクタスタンドアロン オファー Microsoft Teams有効なサブスクリプション (実稼働 EHR 環境でのテスト中にのみ適用されます)。
- ユーザーは、会議を含Microsoft 365またはOffice 365ライセンスを持Teamsがあります。
- Teamsは、医療組織で採用および使用されます。
- システムは、すべての[ソフトウェアとブラウザーの要件を満](../../hardware-requirements-for-the-teams-app.md)たTeams。
- Cerner バージョン 2018 年 11 月以降

## <a name="set-up-the-teams-ehr-connector"></a>EHR コネクタTeams設定する

コネクタの設定には、次のことが必要です。

- [EHR コネクタ構成ポータルを起動する](#launch-the-ehr-connector-configuration-portal)
- [構成情報を入力する](#enter-configuration-information)
- [SMS 通知を有効にする (省略可能)](#enable-sms-notifications-optional)
- [構成を確認して終了する](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> これらの手順は、組織のグローバル管理者Microsoft 365によって完了する必要があります。  

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR コネクタ構成ポータルを起動する

最初に、管理者Microsoft 365 [EHR](https://ehrconnector.teams.microsoft.com) コネクタ構成ポータルを起動し、Microsoft の資格情報を使用してサインインします。

管理者Microsoft 365、統合をテストするために 1 つの部署または複数の部門を構成できます。 構成ポータルでテスト URL と本番 URL を構成します。 必ず、Cerner テスト環境から統合をテストしてから、実稼働環境に移行してください。

### <a name="enter-configuration-information"></a>構成情報を入力する

次に、統合を設定するために、Microsoft 365 管理者は Cerner から Fast Health 相互運用性リソース (FHIR) ベース URL を追加し、環境を指定します。 組織のニーズとテストする環境に応じて、必要な数の FHIR ベース URL を構成します。

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="EHR コネクタ構成ポータルの [構成Teamsページのスクリーンショット。" lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR ベース URL は、サーバーの FHIR API エンドポイントに対応する静的アドレスです。 URL の例は、`https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` です。

- テスト環境と実稼働環境の統合を設定できます。 初期セットアップでは、実稼働環境に移行する前に、テスト環境からコネクタを構成してください。

FHIR ベース URL が検証され、環境が選択された後、[完了] を選択 **します**。 次に、必要に応じて、他の環境の FHIR ベース URL を追加します。

[次 **へ] を** 選択して、次の手順に進みます。

### <a name="enable-sms-notifications-optional"></a>SMS 通知を有効にする (省略可能)

組織で患者の SMS 通知を管理する必要がある場合は、この手順を完了します。 SMS 通知を有効にした場合、患者はスケジュールされた訪問の確認メッセージとアラーム メッセージを受信します。

SMS 通知を有効にするには、管理者Microsoft 365次の手順を実行します。

1. [SMS 通知] ページで、次の両方の同意チェック ボックスをオンにします。

    - Microsoft が組織に代わって患者に SMS 通知を送信できます。
    - 出席者が SMS メッセージの送受信に同意したと確認します。

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="[SMS 通知] ページのスクリーンショット。同意チェック ボックスと電話番号を生成するオプションが表示されています。" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. [ **電話番号] で、[** 新しい **電話番号の生成] を選択** して、組織の電話番号を生成します。 これにより、新しい電話番号を要求して生成するプロセスが開始されます。 このプロセスが完了するには、最大で 2 分かかる場合があります。

    電話番号が生成されると、画面に表示されます。 この番号は、SMS の確認とアラームを患者に送信するために使用されます。 この番号はプロビジョニングされましたが、まだ FHIR ベース URL にリンクされていません。 これは、次の手順で行います。

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="生成された電話番号の例を示すスクリーンショット。" lightbox="media/ehr-admin-cerner-phone-number.png":::

    [完了 **] を** 選択し、[次へ] を **選択します**。

1. 電話番号を FHIR ベース URL にリンクするには、[**SMS** 構成] **電話の** [電話番号] で番号を選択します。 これは、SMS 通知を有効にする FHIR ベース URL ごとに行います。

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="電話番号を FHIR ベース URL にリンクする方法を示すスクリーンショット。" lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    コネクタを初めて構成する場合は、前の手順で入力した FHIR ベース URL が表示されます。 同じ電話番号を複数の FHIR ベース URL にリンクできます。つまり、患者は組織や部門ごとに同じ電話番号から SMS 通知を受信します。

     [**次へ**] を選択します。

### <a name="review-and-finish-the-configuration"></a>構成を確認して終了する

患者とプロバイダーの立ち上げに関する統合レコードが表示されます。 これらのレコードは、Cerner の Virtual Visits 構成を完了するために必要です。 詳細については、Telehealth 統合Cerner-Microsoft Teamsを参照してください。

> [!NOTE]
> 管理者は、Microsoft 365ポータルにサインインして、統合レコードを表示し、必要に応じて構成設定を変更できます。

## <a name="launch-teams-virtual-visits"></a>仮想Teamsを起動する

EHR コネクタの手順と Cerner の構成手順を完了すると、組織はビデオアクセスをサポートする準備が整い、Teams。

### <a name="virtual-visits-prerequisites"></a>Virtual Visits の前提条件

- システムは、すべてのソフトウェアと[ブラウザーの要件を満](../../hardware-requirements-for-the-teams-app.md)たす必要Teams。
- Cerner 組織と自分の組織の間の統合Microsoft 365完了しました。

### <a name="provider-experience"></a>プロバイダー エクスペリエンス

組織内の医療プロバイダーは、PowerChart ポータルからTeamsを使用してアクセスに参加できます。 プロバイダーは、患者ボードに移動する必要があります。このTeamsオプションを使用できます。

そこから、プロバイダーは、アクセス情報の表示、アクセスへの参加、会議リンクの送信を行えます。 1 回サインインすると、プロバイダーは仮想マシンの仮想予定に直接Teams。

プロバイダー エクスペリエンスの主な機能:

- プロバイダーは、サポートされているブラウザーまたはアプリを使用してアクセスTeamsできます。
- プロバイダーは、画面共有、カスタムTeams記録など、サポートされているすべての会議機能を使用できます。
- プロバイダーは、PowerChart で特定の予定の訪問に接続している患者のリアルタイムの更新を確認できます。
- プロバイダー情報は、訪問中に患者に表示されません。

> [!NOTE]
> 医療記録の継続性または保持の目的で必要な会議チャットに入力された情報は、医療機関によってダウンロード、コピー、および記録される必要があります。 チャットは、法的医療記録や指定されたレコード セットを構成する必要があります。 チャットからのメッセージは、管理者が作成した設定に基づいてMicrosoft Teamsされます。

### <a name="patient-experience"></a>患者エクスペリエンス

コネクタは、SMS テキスト メッセージ内のリンクを介して訪問に参加する患者をサポートします。 予約の時点で、患者は SMS テキスト メッセージのリンクをタップして訪問を開始できます。

患者エクスペリエンスの主な機能

- 患者は、デスクトップとモバイルの最新の Web ブラウザーからアクセスに参加できます。このアプリをインストール[Teamsできます](../mobile-browser-join.md)。
- 患者は 1 回のクリックで訪問に参加できます。他のアカウントやサインインは必要ありません。
- 患者は、Microsoft アカウントを作成したり、アクセスを開始するためにサインインしたりする必要はありません。
- 患者は、プロバイダーが参加して受け入れるまでロビーに配置されます。
- 患者は、訪問に参加する前にロビーでビデオとマイクをテストできます。

## <a name="get-insight-into-virtual-visits-usage"></a>Virtual Visits の使用状況に関する分析情報を取得する

Microsoft Teams 管理センターの [Virtual [Visits](../../teams-analytics-and-reports/virtual-visits-usage-report.md) usage](仮想アクセスの使用状況)レポートでは、組織内の仮想アクセスTeamsアクティビティの概要が管理者に表示されます。 このレポートには、EHR システムから実施された EHR 統合Teamsを含む、仮想予定の詳細な分析が表示されます。

ロビーの待機時間やアクセス時間などの主要なメトリックを表示できます。 この情報を使用して使用状況の傾向を把握し、より良いビジネス成果を実現するために Virtual Visits を最適化するのに役立ちます。

## <a name="privacy-and-location-of-data"></a>データのプライバシーと場所

Teams統合すると、統合フローと Virtual Visits フロー中に使用および格納されるデータの量が最適化されます。 このソリューションは、Teams のプライバシーとデータ管理の原則、および Teams のプライバシーで概説されているガイドラインに従います。

EHR Teams、EHR システムから特定可能な個人データや患者または医療プロバイダーの健康記録を保存または転送する必要があります。 EHR コネクタが格納する唯一のデータは、会議のセットアップ中に使用される EHR Teams ID です。

EHR ユーザーの一意の ID は、「[Microsoft 365 の顧客データの保存場所](/microsoft-365/enterprise/o365-data-locations)」で説明されている 3 つの地理的地域のいずれかに保存されます。 会議の参加者が共有するチャット、録音、その他のTeamsは、既存のストレージ ポリシーに従って保存されます。 データ内のデータの場所の詳細については、「Teamsのデータの場所[」をTeams](../../location-of-data-in-teams.md)。

## <a name="related-articles"></a>関連記事

- [Teams Virtual Visits 利用状況レポート](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams EHR コネクタ管理者レポート](ehr-admin-reports.md)
- [医療組織向Teamsの使用を開始する](teams-in-hc.md)
