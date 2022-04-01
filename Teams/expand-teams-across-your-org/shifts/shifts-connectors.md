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
description: Shifts コネクタと、Shifts を使用して従業員管理システムに接続する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 930f4b7a311acc7c34e60b7916071d10349c0313
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592892"
---
# <a name="shifts-connectors"></a>コネクタをシフトする

## <a name="overview"></a>概要

シフト コネクタを使用すると、Microsoft Teams のスケジュール管理ツールである Shifts と、従業員管理 (WFM) システムを統合できます。 接続を設定すると、フロントライン ワーカーは、シフト内から WFM システム内のスケジュールをシームレスに表示および管理できます。

WFM システムをネットワークに接続Teams、フロント ラインの従業員がスケジュールを効率的に管理し、日常のプロセスを効率化してエンゲージメントと生産性を向上させることができます。 フロントライン ワーカーは、スケジュール設定、コミュニケーション、コラボレーションを行う 1 つの場所を持ち、どこからでも、どのデバイスでも作業を行う必要があります。

管理およびオープン ソースの Shifts コネクタを提供しています。 この記事では、Shifts コネクタの概要と動作について説明します。

## <a name="how-shifts-connectors-work"></a>Shifts コネクタの動作

コネクタは WFM システムと Shifts の間でスケジュール データを同期し、組織のスケジュールを最新のTeams。 シフトは、最前線の従業員がスケジュールのニーズに対応する場所です。 WFM システムは、ビジネス ルール、コンプライアンス、インテリジェンスの記録システムです。

コネクタを介したデータ フローでは、両方の方法でスケジュールが常に最新の情報に更新されます。 WFM システムのスケジュールは Shifts に同期されます。 また、シフトのスケジュールに加えた変更は、リアルタイムで WFM システムに同期されます。 レコードのシステムとして、データを Shifts に保存する前に、すべてのビジネス ルールが WFM システムによって適用されます。

## <a name="managed-shifts-connectors"></a>Managed Shifts コネクタ

Managed Shifts コネクタは、パートナーと共同で開発されたコネクタです。 マネージド コネクタは、弊社またはパートナーによってホストおよび管理されます。 マネージド コネクタでは、最小限のセットアップしか必要とされません。

### <a name="microsoft-teams-shifts-connector-for-blue-yonder"></a>Microsoft Teams Blue Yonder 用 Shifts コネクタ
<a name="blue_yonder"> </a>

Blue Yonder Teams Shifts コネクタは、Microsoft によってホストおよび管理されているファースト パーティのオファリングです。 このコネクタを使用すると、Shifts と Blue Yonder Workforce Management (Blue Yonder WFM) バージョン 2020.3、2021.1、または 2021.2 を統合して、スケジュールを管理し、最新の状態に維持できます。  

> [!NOTE]
> Blue Yonder WFM バージョン 2020.3 または 2021.1 を使用している場合は、2020.3.0.4 または 2021.1.0.3 パッチを適用します。 この修正プログラムは、ユーザーが Shifts で永続的なエラー メッセージを受け取る問題を修正します。 また、ユーザーが Shifts で可用性を更新できる問題も修正されます。

:::image type="content" source="../../media/shifts-connector-blue-yonder.png" alt-text="モバイル デバイスの Shifts でのスワップ要求、デスクトップ上の Teams での承認の要求、Blue Yonder WFM のスケジュールを示すスクリーンショット。" lightbox="../../media/shifts-connector-blue-yonder.png":::

フロントライン マネージャーは、次の方法を使用できます。

- Blue Yonder WFM でシフトとスケジュールを公開し、シフトで表示します。
- Blue Yonder WFM で開いているシフトを作成、管理、割り当て、シフトで表示します。
- Shifts で Blue Yonder WFM で作成されたオープン シフトを割り当てる。
- Blue Yonder WFM で休み時間を作成、編集、削除し、シフトで表示します。
- Blue Yonder WFM と Shift の両方で、worker からのスケジュール要求を表示および承認します。
- Blue Yonder WFM で worker の空き時間情報を設定および更新し、Shifts で表示します。

フロントライン ワーカーは次の作業を行います。

- 自分のシフトとチームのシフトとスケジュールをシフトで確認します。
- シフトで、休み、シフトを開き、シフトを入れ替えます。
- シフトで空き時間情報を設定します。

現在、次のアクションはサポートされていません。

- Shifts でシフトを追加、編集、削除、保存、または公開します。
- Shifts で時間を追加、編集、削除、保存、または公開します。
- Shifts で開いているシフトを追加、編集、削除、保存、または公開します。

フロントライン マネージャーまたはワーカーが Shifts でこれらのアクションを実行しようとすると、アクションがサポートされていないことを知らせるメッセージが表示されます。

#### <a name="example-scenario"></a>シナリオ例

マネージャーのTeams Blue Yonder WFM でスケジュールを発行します。 スタッフ メンバーである Alex は、モバイル デバイスTeamsで通知を受け取り、スケジュールと割り当てられたシフトを表示します。

Alex は、ある程度の時間を取り、Shifts を使用して 1 日の休みを要求する必要があります。 要求は、コネクタを介して Blue Yonder WFM にリアルタイムで送信されます。 Blue Yonder WFM では、要求がビジネス ルールに準拠しており、要求が作成されます。 Blue Yonder WFM で要求が表示および承認され、承認が承認されたTeams。 (また、Shifts で要求を表示および承認できます)。 Alex は、要求が承認Teams、更新されたスケジュールを表示する通知を受け取るメッセージを表示します。

Alex はシフトを同僚と交換したいと思っています。 Shifts では、Alex は Blue Yonder WFM のビジネス ルールに基づいてスワップの対象となるすべてのシフトの一覧を表示します。 Alex は、現在 Gena に割り当てられているシフトを選択します。 Gena は、モバイル Teamsで通知され、スワップ要求を受け入れる。 Blue Yonder WFM に承認が同期され、Shifts で要求が表示され、承認が承認されます。 (Blue Yonder WFM では、この要求を表示して承認する方法も示します)。 Alex と Gena は、Teamsに通知され、更新されたスケジュールを表示します。

#### <a name="set-up-a-connection"></a>接続を設定する

コネクタを使用して Shifts と Blue Yonder WFM を統合する手順はわずかです。 接続をすばやく設定するには、Microsoft 365 管理センター Shifts コネクタ ウィザードを使用します。 ウィザードは、選択した設定に基づいてコネクタを構成し、接続を作成します。 PowerShell を使用する場合は、接続に使用できる PowerShell スクリプトも用意されています。

詳細なガイダンスについては、以下を参照してください。

- [Shifts コネクタ ウィザードを使用して Shifts を Blue Yonder Workforce Management に接続する](shifts-connector-wizard.md)
- [PowerShell を使用してシフトを Blue Yonder Workforce Management に接続する](shifts-connector-blue-yonder-powershell-setup.md)

接続を設定した後は、PowerShell を使用して、必要に応じていつでも接続設定を更新および変更できます。 コネクタ自体については、アップグレードやメンテナンスについて心配する必要はありません。 この問題は、弊社で行います。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>再帰用の Reflexis Shifts コネクタMicrosoft Teams

Zebra がホストおよび管理するMicrosoft Teams用の Reflexis Shifts コネクタ。 このコネクタを使用すると、Shifts と Reflexis WFM システムを統合して、スケジュールを管理し、最新の状態に維持できます。

フロントラインワーカーは Teams のシフトでスケジュールにアクセスできます。要求は Shifts から Reflexis Workforce Scheduler (RWS) に同期されます。 RWS で作成された要求とシフトの状態は、Teams の Shifts に同期されます。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="モバイル デバイスのシフトの一覧と、再帰のスケジュールを示すスクリーンショット。" lightbox="../../media/shifts-connector-reflexis.png":::

フロントライン マネージャーは、次の方法を使用できます。

- 再帰でシフトとスケジュールを公開し、シフトで表示します。
- 再帰とシフトの両方でシフトを編集します。
- 再帰とシフトの両方で、開いているシフトを作成、管理、および割り当てる。
- 再帰とシフトの両方で、worker からのスケジュール要求を表示および承認します。

フロントライン ワーカーは次の作業を行います。

- 自分のシフトとチームのシフトとスケジュールをシフトで確認します。
- シフトで休み、シフトを開き、シフトを交換して提供します。

詳細については、 にアクセスしてください https://connect.zebra.com/microsoft-connectors。

## <a name="open-source-shifts-connectors"></a>オープン ソースの Shifts コネクタ

オープン ソースの Shifts コネクタは、Shifts と API に基Graph[統合です](/graph/api/resources/shift)。 次のオープン ソース コネクタを使用できます。

- オンプレミスの Kronos-to-Teams WFC
- JDA-to-Teams Shifts コネクタ (Blue Yonder バージョン 2017 から 2020.2 の場合)

各コネクタには、デプロイと構成の詳細なガイダンスが付属しています。 Azure Resource Manager (ARM) デプロイ スクリプトが含まれています。このスクリプトを使用すると、必要なすべてのサービスを Microsoft Azure。 ソース コードとデプロイ スクリプトは、GitHub[できます](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)。 この方法でデプロイするか、ニーズに合わせてカスタマイズまたは拡張できます。

詳細については、「実稼働対応 [の Shifts コネクタ」を参照してください](/microsoftteams/platform/samples/shifts-wfm-connectors)。

## <a name="related-articles"></a>関連記事

- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
