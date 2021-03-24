---
title: Teams にアップグレードするための前提条件と環境の依存関係
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: このガイダンスを使用して、組織に Teams を展開するための前提条件と環境の依存関係について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ceca08be6d69a10fe84daa64d0da4e31c61c67c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092195"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Teams の前提条件と環境の依存関係

![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")

この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。 次の手順に進む前に、前のステージからこれらのアクティビティを完了したと確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams は複数の Microsoft 365 サービスと Office 365 サービスを組み合わせたため、これらのサービスの適切な実装と運用に依存します。 これらのサービスには、SharePoint Online、Exchange Online、OneDrive for Business が含まれますが、これらに限定される機能があります。

すべてのサービスが必要な場合は、必ずしもすべてのサービスを実装することを強くお勧めします。 特定のサービスを実装しない場合、Teams が組織に提供できる機能に影響します。 たとえば、SharePoint Online を実装する必要はありません。Teams は、グループ会話でのファイル共有などの特定の機能を SharePoint Online に依存します。そのため、このサービスを実装しない場合、クライアントを通じて提供される機能が削減されます。

前提条件と Teams が他のテクノロジとやり取りする方法については、次の記事を参照してください。

- 組織が Microsoft 365 または 365 ワークロードを展開Office場合は、「使用を開始する」を [参照してください](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 組織で Microsoft 365 または Office 365 の確認済みドメインを追加または構成されていない場合は、「ドメインに関する [FAQ」を参照してください](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

- 組織が Azure Active Directory と ID を同期しない場合は、「Microsoft Teams の ID モデルと認証」 [を参照してください](identify-models-authentication.md)。

- 組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](Exchange-Teams-interact.md)」をご覧ください。

- 組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)」をご覧ください。

- [Microsoft 365 グループと Microsoft Teams の対話方法について説明します](Office-365-groups.md)。

- 組織が教育機関で学生情報システムを使用している場合は、Microsoft Teams を展開する前に [、「Microsoft School Data Sync](/schooldatasync) へようこそ」を参照してください。

- 組織で公衆交換電話網 (PSTN) 通話オプションを検討している場合は、「音声 - 電話システムと[](calling-plan-landing-page.md)[PSTN](cloud-voice-landing-page.md)接続、最適な通話プラン、[](direct-routing-landing-page.md)電話システムダイレクト ルーティング」を参照してください。

- Teams を展開する前に、すべてのネットワーク要件を満たしていることを確認するには [、「Microsoft Teams](prepare-network.md)用に組織のネットワークを準備する」を参照してください。

- 現在 Skype for Business Online Connector を使用してサービスを管理している場合は、Teams PowerShell モジュールに移動し、既存の PowerShell スクリプトを更新する必要があります。 詳細 [については、「Skype for Business Online Connector から Teams PowerShell](teams-powershell-move-from-sfbo.md) モジュールに移動する」を参照してください。

使用している環境がすべての該当する前提条件を満たしていることを確認した後、Teams の現在 [の環境を評価します](upgrade-plan-journey-evaluate-environment.md)。