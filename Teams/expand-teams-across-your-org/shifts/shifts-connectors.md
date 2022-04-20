---
title: コネクタをシフトする
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Shifts コネクタと、それらを使用して Shifts を従業員管理システムに接続する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64592892"
---
# <a name="shifts-connectors"></a>コネクタをシフトする

## <a name="overview"></a>概要

Shifts コネクタを使用すると、Microsoft Teamsのスケジュール管理ツールである Shifts を従業員管理 (WFM) システムと統合できます。 接続を設定すると、フロントライン ワーカーは Shifts 内から WFM システムでスケジュールをシームレスに表示および管理できます。

WFM システムをTeamsに接続することで、現場の従業員はスケジュールをより効果的に管理し、より高いエンゲージメントと生産性を実現するために日常のプロセスを合理化できます。 現場のワーカーは、スケジュール設定、コミュニケーション、コラボレーションを行うための 1 つの場所を持ち、どこからでも、あらゆるデバイスで作業を完了する必要があります。

マネージドおよびオープンソースの Shifts コネクタを提供しています。 この記事では、Shifts コネクタとその動作の概要について説明します。

## <a name="how-shifts-connectors-work"></a>Shifts コネクタのしくみ

コネクタは、WFM システムと Shifts の間でスケジュール データを同期し、組織のスケジュールをTeamsにします。 シフトは、現場のワーカーがスケジュールのニーズに応じて取り組む場所です。 WFM システムは、ビジネス ルール、コンプライアンス、インテリジェンスの記録システムです。

コネクタを介したデータ フローは、両方の方法でスケジュールが常に最新であることを確認します。 WFM システムのスケジュールは Shifts に同期されます。 また、Shifts でスケジュールに加えられた変更は、WFM システムにリアルタイムで同期されます。 レコードのシステムとして、データが Shifts に保存される前にすべてのビジネス ルールが WFM システムによって適用されます。

## <a name="managed-shifts-connectors"></a>マネージド シフト コネクタ

マネージド シフト コネクタは、パートナーと共同で開発されたコネクタです。 マネージド コネクタは、Microsoft またはパートナーによってホストおよび管理されます。 マネージド コネクタでは、最小限のセットアップのみが必要です。

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Blue Yonder 用の Microsoft Teams Shifts コネクタ
<a name="blue_yonder"> </a>

Blue Yonder 用の Teams Shifts コネクタは、Microsoft によってホストおよび管理されているファースト パーティ製品です。 このコネクタを使用すると、Shifts と Blue Yonder Workforce Management (Blue Yonder WFM) バージョン 2020.3、2021.1、または 2021.2 を統合してスケジュールを管理し、最新の状態に保つことができます。  

> [!NOTE]
> Blue Yonder WFM バージョン 2020.3 または 2021.1 がある場合は、2020.3.0.4 または 2021.1.0.3 パッチを適用します。 この修正プログラムは、ユーザーが Shifts で永続的なエラー メッセージを受け取る問題を修正します。 また、ユーザーが Shifts で可用性を更新できない問題も修正されます。

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="モバイル デバイスの Shifts でのスワップ要求、デスクトップでのTeamsでの承認の要求、Blue Yonder WFM のスケジュールを示すスクリーンショット。" lightbox="../../media/shifts-connector-blue-yonder.png":::

フロントライン マネージャーは次のことができます。

- Blue Yonder WFM でシフトとスケジュールを公開し、Shifts で表示します。
- Blue Yonder WFM でオープン シフトを作成、管理、割り当て、Shifts で表示します。
- Shifts の Blue Yonder WFM で作成されたオープン シフトを割り当てます。
- Blue Yonder WFM で休暇を作成、編集、削除し、Shifts で表示します。
- Blue Yonder WFM と Shifts の両方のワーカーからのスケジュール要求を表示および承認します。
- Blue Yonder WFM でワーカーの可用性を設定および更新し、Shifts で表示します。

フロントライン ワーカーは次のことができます。

- Shifts で、自分とチームのシフトとスケジュールを確認します。
- Shifts で、オフ、オープン シフト、スワップ シフトを要求します。
- Shifts で可用性を設定します。

現在、次のアクションはサポートされていません。

- Shifts でシフトを追加、編集、削除、保存、発行します。
- Shifts で休暇を追加、編集、削除、保存、公開します。
- Shifts で開いているシフトを追加、編集、削除、保存、公開します。

フロントライン マネージャーまたはワーカーが Shifts でこれらのアクションのいずれかを実行しようとすると、アクションがサポートされていないことを知らせるメッセージが表示されます。

#### <a name="example-scenario"></a>シナリオ例

マネージャーである Eden は、コネクタを介してTeamsの Shifts に同期される Blue Yonder WFM でスケジュールを公開します。 スタッフである Alex は、モバイル デバイスのTeamsで通知を受け取り、スケジュールと割り当てられたシフトを表示します。

Alex は少し時間を取る必要があり、Shifts を使用して 1 日の休暇を要求します。 要求は、コネクタを介して Blue Yonder WFM にリアルタイムで送信されます。 Blue Yonder WFM により、要求がビジネス ルールに準拠し、要求が作成されます。 Blue Yonder WFM で要求が表示され、承認され、承認がTeamsに同期されます。 (Eden は、Shifts で要求を表示および承認することもできます)。 Alex は、要求が承認されたことをTeamsに通知され、更新されたスケジュールが表示されます。

Alex は、シフトを同僚と入れ替えたいと考えています。 Shifts では、Alex は Blue Yonder WFM のビジネス ルールに基づいてスワップの対象となるすべてのシフトの一覧を表示します。 Alex は、現在 Gena に割り当てられているシフトを選択します。 Gena はモバイル デバイス上のTeamsで通知を受け取り、スワップ要求を受け入れます。 Eden は Shifts で要求を確認して承認し、承認は Blue Yonder WFM に同期されます。 (Blue Yonder WFM で要求を確認して承認することもできます)。 Alex と Gena はTeamsで通知を受け取り、更新されたスケジュールを表示します。

#### <a name="set-up-a-connection"></a>接続を設定する

コネクタを使用して Shifts と Blue Yonder WFM を統合するには、いくつかの手順を実行します。 Microsoft 365 管理センターの Shifts コネクタ ウィザードを使用して、接続をすばやく設定できます。 ウィザードは、選択した設定に基づいてコネクタを構成し、接続を作成します。 PowerShell を使用する場合は、接続に使用できる PowerShell スクリプトも用意されています。

詳細なガイダンスについては、次を参照してください。

- [Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する](shifts-connector-wizard.md)
- [PowerShell を使用してシフトを Blue Yonder Workforce Management に接続する](shifts-connector-blue-yonder-powershell-setup.md)

接続が設定されたら、PowerShell を使用して、必要に応じていつでも接続設定を更新および変更できます。 コネクタ自体については、アップグレードやメンテナンスについて心配する必要はありません。 その処理を行います。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>Microsoft Teams用の Reflectionis Shifts コネクタ

Microsoft Teams用の Reflectionis Shifts コネクタは、Zebra によってホストおよび管理されます。 このコネクタを使用すると、Shifts と Reflectionis WFM システムを統合してスケジュールを管理し、それらを最新の状態に保つことができます。

フロントライン ワーカーは、Teamsのシフトでスケジュールにアクセスでき、その要求は Shifts から Reflectionis Workforce Scheduler (RWS) に同期されます。 RWS で作成された要求とシフトの状態は、Teamsの Shifts に同期されます。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="モバイル デバイスのシフトの一覧と、Reflectionis のスケジュールを示すスクリーンショット。" lightbox="../../media/shifts-connector-reflexis.png":::

フロントライン マネージャーは次のことができます。

- Shifts でシフトとスケジュールを公開し、Shifts で表示します。
- Reflectionis と Shifts の両方でシフトを編集します。
- Reflectionis と Shifts の両方でオープン シフトを作成、管理、割り当てます。
- Reflectionis と Shifts の両方のワーカーからのスケジュール要求を表示および承認します。

フロントライン ワーカーは次のことができます。

- Shifts で、自分とチームのシフトとスケジュールを確認します。
- Shifts で、休暇の要求、シフトのオープン、シフトのスワップとオファーを行います。

詳細については、次のページを https://connect.zebra.com/microsoft-connectors参照してください。

## <a name="open-source-shifts-connectors"></a>オープンソースの Shifts コネクタ

オープンソースの Shifts コネクタは、[Shifts Graph API](/graph/api/resources/shift) 上に構築されたコミュニティ主導の統合です。 次のオープン ソース コネクタを使用できます。

- Kronos-to-Teams WFC オンプレミス
- JDA からTeams Shifts コネクタ (Blue Yonder バージョン 2017 から 2020.2 の場合)

各コネクタには、詳細なデプロイと構成のガイダンスが付属しています。 これには、Microsoft Azureで必要なすべてのサービスをホストできる Azure Resource Manager (ARM) デプロイ スクリプトが含まれています。 ソース コードとデプロイ スクリプトは、[GitHub リポジトリ](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)でダウンロードできます。 そのままデプロイすることも、ニーズに合わせてカスタマイズまたは拡張することもできます。

詳細については、 [実稼働対応の Shifts コネクタに関するページを](/microsoftteams/platform/samples/shifts-wfm-connectors)参照してください。

## <a name="related-articles"></a>関連記事

- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
