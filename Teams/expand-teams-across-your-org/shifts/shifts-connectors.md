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
ms.openlocfilehash: 7a5e330710fcbdbda6c82db2643e1ed7c0fa5a26
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192488"
---
# <a name="shifts-connectors"></a>コネクタをシフトする

## <a name="overview"></a>概要

Shifts コネクタを使用すると、Microsoft Teams のスケジュール管理ツールである Shifts と、従業員管理 (WFM) システムを統合できます。 接続を設定すると、フロントライン ワーカーは、シフト内から WFM システム内のスケジュールをシームレスに表示および管理できます。

WFM システムを Teamsに接続すると、フロント ラインの従業員はスケジュールを効率的に管理し、エンゲージメントと生産性を高める日常的なプロセスを合理化できます。 フロントライン ワーカーは、スケジュール設定、コミュニケーション、コラボレーションを行う 1 つの場所を持ち、どこからでも、どのデバイスでも作業を行う必要があります。

管理およびオープン ソースの Shifts コネクタを提供しています。 この記事では、Shifts コネクタの概要と動作について説明します。

## <a name="how-shifts-connectors-work"></a>Shifts コネクタの動作

コネクタは WFM システムとシフトの間でスケジュール データを同期し、組織のスケジュールを新しいTeams。 シフトは、最前線の従業員がスケジュールのニーズに対応する場所です。 WFM システムは、ビジネス ルール、コンプライアンス、インテリジェンスの記録システムです。

コネクタを介したデータ フローでは、両方の方法でスケジュールが常に最新の情報に更新されます。 WFM システムのスケジュールは Shifts に同期されます。 また、シフトのスケジュールに加えた変更は、リアルタイムで WFM システムに同期されます。 レコードのシステムとして、データを Shifts に保存する前に、すべてのビジネス ルールが WFM システムによって適用されます。

## <a name="managed-shifts-connectors"></a>Managed Shifts コネクタ

Managed Shifts コネクタは、パートナーと共同で開発されたコネクタです。 マネージド コネクタは、弊社またはパートナーによってホストおよび管理されます。 マネージド コネクタでは、最小限のセットアップしか必要とされません。

### <a name="reflexis-shifts-connector-for-microsoft-teams"></a>再帰用の Shifts コネクタMicrosoft Teams

Zebra がホストおよび管理するMicrosoft Teams用の Reflexis Shifts コネクタ。 このコネクタを使用すると、Shifts と Reflexis WFM システムを統合して、スケジュールを管理し、最新の状態に維持できます。

フロントラインワーカーは Teams のシフトでスケジュールにアクセスできます。要求は Shifts から Reflexis Workforce Scheduler (RWS) に同期されます。 RWS で作成された要求とシフトの状態は、Teams の Shifts に同期されます。

:::image type="content" source="../../media/shifts-connector-reflexis.png" alt-text="モバイル デバイスのシフトの一覧と、再帰のスケジュールを示すスクリーンショット" lightbox="../../media/shifts-connector-reflexis.png":::

フロントライン マネージャーは、次の方法を使用できます。

- 再帰でシフトとスケジュールを公開し、シフトで表示します。
- 再帰とシフトの両方でシフトを編集します。
- 再帰とシフトの両方で、開いているシフトを作成、管理、および割り当てる。
- 再帰とシフトの両方で、worker からのスケジュール要求を表示および承認します。

フロントライン ワーカーは次の作業を行います。

- 自分のシフトとチームのシフトとスケジュールをシフトで確認します。
- シフトで休み、シフトを開き、シフトを交換して提供します。

詳細については、 にアクセスしてください https://connect.zebra.com/microsoft-connectors 。

## <a name="open-source-shifts-connectors"></a>オープン ソースの Shifts コネクタ

オープン ソースの Shifts コネクタは[、Shifts](/graph/api/resources/shift)と API に基Graph統合です。 次のオープン ソース コネクタを使用できます。

- オンプレミスの Kronos-to-Teams WFC
- JDA-to-Teams Shifts コネクタ (Blue Yonder バージョン 2017 ~ 2020.2)

各コネクタには、デプロイと構成の詳細なガイダンスが付属しています。 Azure Resource Manager (ARM) デプロイ スクリプトが含まれています。このスクリプトを使用すると、すべての必要なサービスを Microsoft Azure。 ソース コードとデプロイ スクリプトは、GitHub[リポジトリでダウンロードできます](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)。 この方法でデプロイするか、ニーズに合わせてカスタマイズまたは拡張できます。

詳細については、「実稼働対応 [の Shifts コネクタ」を参照してください](/microsoftteams/platform/samples/shifts-wfm-connectors)。

## <a name="related-articles"></a>関連記事

- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
