---
title: Teamsを使用した仮想アクセス - Cerner EHR への統合
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
description: Teams EHR コネクタを統合して、組織内の医療プロバイダーが Cerner EHR システムから直接Teamsで患者や他のプロバイダーと仮想訪問を行えるようにする方法について説明します。
ms.openlocfilehash: b5a5a860036b3b561d5a6e18a13b71e072998aa4
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64703693"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Teamsを使用した仮想アクセス - Cerner EHR への統合

Microsoft Teams電子正常性レコード (EHR) コネクタを使用すると、臨床医は簡単に仮想患者の訪問を開始したり、Cerner EHR システムから直接Microsoft Teams別のプロバイダーに相談したりできます。 Microsoft 365 クラウド上に構築されたTeamsは、HIPAA、HITECH 認定などのコンプライアンスをサポートする 1 つのハブで、チャット、ビデオ、音声、ヘルスケア ツールとの簡単で安全なコラボレーションとコミュニケーションを実現します。

Teamsのコミュニケーションとコラボレーション プラットフォームにより、臨床医は断片化されたシステムの混乱を簡単に切り取り、可能な限り最善のケアを提供することに集中できます。 Teams EHR コネクタを使用すると、次のことができます。

- 統合された臨床ワークフローを使用して、Cerner EHR システムから仮想訪問をTeams行います。
- 患者が電子メールまたは SMS 通知からTeams Virtual Visits に参加できるようにします。
- EHR に接続された訪問の消費データ レポートとカスタマイズ可能な通話品質情報を表示します。

この記事では、Cerner プラットフォームと統合するようにTeams EHR コネクタを設定して構成する方法について説明します。 また、Cerner EHR システムからのTeams Virtual Visits エクスペリエンスの概要についても説明します。

## <a name="before-you-begin"></a>はじめに

> [!NOTE]
> 統合を有効にする前に、Cerner 担当者に問い合わせて Cerner 統合ガイドを確認してください。

### <a name="prerequisites"></a>前提条件

医療機関でTeams EHR コネクタを統合する前に、次のものが必要です。

- EHR コネクタスタンドアロン オファー Microsoft Teamsアクティブなサブスクリプションです (運用環境の EHR 環境でのテスト中にのみ適用)。
- ユーザーは、Teams会議を含む適切なMicrosoft 365またはOffice 365ライセンスを持っています。
- Teamsが採用され、医療組織で使用されます。
- システムは、Teamsのすべての[ソフトウェアとブラウザーの要件](../../hardware-requirements-for-the-teams-app.md)を満たしています。
- Cerner バージョン 2018 年 11 月以降

## <a name="set-up-the-teams-ehr-connector"></a>Teams EHR コネクタを設定する

コネクタの設定には、次のことが必要です。

- [EHR コネクタ構成ポータルを起動する](#launch-the-ehr-connector-configuration-portal)
- [構成情報を入力する](#enter-configuration-information)
- [SMS 通知を有効にする (省略可能)](#enable-sms-notifications-optional)
- [構成を確認して終了する](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> これらの手順は、組織内のMicrosoft 365グローバル管理者が完了する必要があります。  

### <a name="launch-the-ehr-connector-configuration-portal"></a>EHR コネクタ構成ポータルを起動する

開始するには、Microsoft 365管理者が [EHR コネクタ構成ポータル](https://ehrconnector.teams.microsoft.com)を起動し、Microsoft 資格情報を使用してサインインします。

Microsoft 365管理者は、統合をテストするために 1 つの部署または複数の部門を構成できます。 構成ポータルでテスト URL と本番 URL を構成します。 運用に移行する前に、Cerner テスト環境から統合をテストしてください。

### <a name="enter-configuration-information"></a>構成情報を入力する

次に、統合を設定するために、Microsoft 365管理者は Cerner から Fast Health 相互運用性リソース (FHIR) ベース URL を追加し、環境を指定します。 組織のニーズとテストする環境に応じて、必要な数の FHIR ベース URL を構成します。

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Teams EHR コネクタ構成ポータルの [構成情報] ページのスクリーンショット。" lightbox="media/ehr-admin-cerner-configuration.png":::

- FHIR ベースの URL は、サーバー FHIR API エンドポイントに対応する静的アドレスです。 URL の例は、`https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` です。

- テスト環境と運用環境の統合を設定できます。 初期セットアップでは、運用環境に移行する前に、テスト環境からコネクタを構成することをお勧めします。

FHIR ベース URL が検証され、環境が選択されたら、[完了] を選択 **します**。 次に、必要に応じて、他の環境用の FHIR ベース URL をさらに追加します。

**[次へ**] を選択して、次の手順に進みます。

### <a name="enable-sms-notifications-optional"></a>SMS 通知を有効にする (省略可能)

組織が患者の SMS 通知を Microsoft が管理することを望む場合は、この手順を完了します。 SMS 通知を有効にすると、患者はスケジュールされた訪問の確認メッセージとリマインダー メッセージを受け取ります。

SMS 通知を有効にするには、Microsoft 365管理者が次の操作を行います。

1. SMS 通知ページで、次の両方の同意チェック ボックスをオンにします。

    - Microsoft が組織に代わって患者に SMS 通知を送信できるようにします。
    - 出席者が SMS メッセージの送受信に同意したことを確認します。

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="SMS 通知ページのスクリーンショット。同意チェック ボックスと電話番号を生成するオプションが表示されています。" lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. [ **電話番号**] で [ **新しい電話番号の生成** ] を選択して、組織の電話番号を生成します。 これにより、新しい電話番号を要求して生成するプロセスが開始されます。 このプロセスが完了するまでに最大 2 分かかる場合があります。

    電話番号が生成されると、画面に表示されます。 この番号は、SMS の確認とリマインダーを患者に送信するために使用されます。 この番号はプロビジョニングされていますが、FHIR ベース URL にリンクされていません。 次の手順で行います。

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="生成される電話番号の例を示すスクリーンショット。" lightbox="media/ehr-admin-cerner-phone-number.png":::

    [ **完了] を** 選択し、[ **次へ**] を選択します。

1. 電話番号を FHIR ベース URL にリンクするには、[**SMS 構成**] セクション **の [電話番号**] で番号を選択します。 SMS 通知を有効にする FHIR ベース URL ごとにこれを行います。

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="電話番号を FHIR ベース URL にリンクする方法を示すスクリーンショット。" lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    コネクタを初めて構成する場合は、前の手順で入力した FHIR ベースの URL が表示されます。 同じ電話番号を複数の FHIR ベースの URL にリンクできます。つまり、患者は異なる組織や部署に対して同じ電話番号から SMS 通知を受け取ります。

     [**次へ**] を選択します。

### <a name="review-and-finish-the-configuration"></a>構成を確認して終了する

患者とプロバイダーの起動に関する統合レコードが表示されます。 これらのレコードは、Cerner で Virtual Visits 構成を完了するために必要です。 詳細については、Cerner-Microsoft Teams Telehealth 統合ガイドを参照してください。

> [!NOTE]
> Microsoft 365管理者はいつでも、構成ポータルにサインインして統合レコードを表示し、必要に応じて構成設定を変更できます。

## <a name="launch-teams-virtual-visits"></a>仮想アクセスTeams起動する

EHR コネクタの手順と Cerner の構成手順を完了すると、組織はTeamsでのビデオ アクセスをサポートする準備が整いました。

### <a name="virtual-visits-prerequisites"></a>Virtual Visits の前提条件

- システムは、Teamsのすべての[ソフトウェアとブラウザーの要件](../../hardware-requirements-for-the-teams-app.md)を満たしている必要があります。
- Cerner 組織とMicrosoft 365組織の間の統合セットアップが完了しました。

### <a name="provider-experience"></a>プロバイダー エクスペリエンス

組織内の医療プロバイダーは、PowerChart ポータルからTeamsを使用して訪問に参加できます。 プロバイダーは、Teams オプションが使用可能な患者ボードに移動する必要があります。

そこから、プロバイダーは訪問情報を表示し、訪問に参加し、会議のリンクを送信できます。 1 回限りのサインイン後、プロバイダーはTeamsの仮想予定に直接移動します。

プロバイダー エクスペリエンスの主な機能:

- プロバイダーは、サポートされているブラウザーまたはTeams アプリを使用して、アクセスに参加できます。
- プロバイダーは、画面共有、カスタム背景、記録など、サポートされているすべてのTeams会議機能を使用できます。
- プロバイダーは、PowerChart で特定の予定の訪問に接続している患者のリアルタイムの更新を確認できます。
- プロバイダー情報は、訪問中に患者に表示されません。

> [!NOTE]
> 医療記録の継続性または保有目的に必要な会議チャットに入力されたすべての情報は、医療提供者がダウンロード、コピー、および注意する必要があります。 チャットは、法的な医療記録や指定されたレコード セットを構成しません。 チャットからのメッセージは、Microsoft Teams管理者によって作成された設定に基づいて保存されます。

### <a name="patient-experience"></a>患者エクスペリエンス

コネクタは、SMS テキスト メッセージ内のリンクを介して訪問に参加する患者をサポートします。 予定の時点で、患者は SMS テキスト メッセージのリンクをタップして訪問を開始できます。

患者エクスペリエンスの主な機能

- 患者は、[Teams アプリをインストールしなくても、デスクトップとモバイル上の最新の Web ブラウザー](../browser-join.md)からの訪問に参加できます。
- 患者はワンクリックで訪問に参加でき、他のアカウントやサインインは必要ありません。
- 患者は、Microsoft アカウントを作成したり、アクセスを開始するためにサインインしたりする必要はありません。
- 患者は、プロバイダーが参加して入院するまでロビーに配置されます。
- 患者は、訪問に参加する前にロビーでビデオとマイクをテストできます。

## <a name="get-insight-into-virtual-visits-usage"></a>Virtual Visits の使用状況に関する分析情報を取得する

Microsoft Teams管理センターの [Virtual Visits 使用状況レポート](../../teams-analytics-and-reports/virtual-visits-usage-report.md)では、管理者に組織内のTeams Virtual Visits アクティビティの概要が表示されます。 レポートには、EHR システムから実施された EHR 統合会議Teams含む、仮想予定の詳細な分析が表示されます。

ロビーの待機時間やアクセス時間などの主要なメトリックを表示できます。 この情報を使用して、使用傾向の分析情報を取得し、Virtual Visits を最適化してビジネス成果を向上させるのに役立ちます。

## <a name="privacy-and-location-of-data"></a>データのプライバシーと場所

EHR システムへの統合Teams、統合および Virtual Visits フロー中に使用および格納されるデータの量を最適化します。 このソリューションは、Teams のプライバシーとデータ管理の原則、および Teams のプライバシーで概説されているガイドラインに従います。

Teams EHR コネクタは、EHR システムから識別可能な個人データや患者または医療提供者の健康記録を保存または転送しません。 EHR コネクタが格納する唯一のデータは、会議のセットアップ中に使用される EHR ユーザーの一意の ID Teams。

EHR ユーザーの一意の ID は、「[Microsoft 365 の顧客データの保存場所](/microsoft-365/enterprise/o365-data-locations)」で説明されている 3 つの地理的地域のいずれかに保存されます。 会議参加者がTeamsで共有するすべてのチャット、レコーディング、その他のデータは、既存のストレージ ポリシーに従って保存されます。 Teams内のデータの場所の詳細については、「[Teamsのデータの場所」を](../../location-of-data-in-teams.md)参照してください。

## <a name="related-articles"></a>関連記事

- [Teams Virtual Visits の使用状況レポート](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [EHR コネクタ管理者レポートのTeams](ehr-admin-reports.md)
- [医療機関向けのTeamsとの概要](teams-in-hc.md)
