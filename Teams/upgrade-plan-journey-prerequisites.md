---
title: Teamsにアップグレードするための前提条件と環境の依存関係
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: このガイダンスを使用して、組織にTeamsを展開するための前提条件と環境の依存関係について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f10df8849e6efe4e6ceac38cb46d118dff5a8ff8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725456"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Teamsの前提条件と環境の依存関係

![技術的準備段階を強調したアップグレード体験図。](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")

この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。 続行する前に、前の段階でこれらのアクティビティが完了したことを確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teamsは、複数のMicrosoft 365サービスとOffice 365 サービスを組み合わせたものであるため、これらのサービスの正しい実装と運用に依存します。 これらのサービスには、オンライン、Exchange Online、OneDrive for Business SharePoint含まれますが、これらに限定されません。

すべてのサービスが必要なわけではありませんが、すべてのサービスを実装することを非常に推奨します。 特定のサービスを実装しないことを選択した場合、Teamsが組織に提供できる機能に影響します。 たとえば、SharePoint Online を実装する必要はありませんが、Teamsグループ会話でのファイル共有などの特定の機能についてはSharePoint Online に依存しているため、このサービスを実装しないと、クライアントから提供される機能が低下します。

前提条件と、Teamsが他のテクノロジと対話する方法については、次の記事を参照してください。

- 組織がMicrosoft 365ワークロードまたはOffice 365ワークロードをデプロイしていない場合は、[概要](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)を参照してください。

- 組織で、Microsoft 365またはOffice 365の検証済みドメインを追加または構成していない場合は、「[ドメインに関する FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)」を参照してください。

- 組織がAzure Active Directoryに ID を同期していない場合は、Microsoft Teams[の ID モデルと認証に](identify-models-authentication.md)関する説明を参照してください。

- 組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](Exchange-Teams-interact.md)」をご覧ください。

- 組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)」をご覧ください。

- [Microsoft 365 グループとMicrosoft Teamsの相互作用](Office-365-groups.md)について説明します。

- 組織が教育機関であり、学生情報システムを使用している場合は、[Microsoft Teamsを展開する前に、「Microsoft 学校データ同期へようこそ](/schooldatasync)」を参照してください。

- 組織で公衆交換電話網 (PSTN) の通話オプションを検討している場合は、「[音声 - 電話システムと PSTN の接続](cloud-voice-landing-page.md)、[通話プランが適している通話プラン](calling-plan-landing-page.md)、および[ダイレクト ルーティングの電話システム](direct-routing-landing-page.md)」を参照してください。

- Teamsを展開する前にすべてのネットワーク要件が満たされていることを確認するには、「[組織のネットワークをMicrosoft Teamsに準備](prepare-network.md)する」を参照してください。

- 現在 Skype for Business Online Connector を使用してサービスを管理している場合は、Teams PowerShell モジュールに移動し、既存の PowerShell スクリプトを更新する必要があります。 詳しくは、「[Skype for Business Online Connector から Teams PowerShell モジュールに移動する](teams-powershell-move-from-sfbo.md)」をご覧ください。

環境が適用可能なすべての前提条件を満たしていることを確認したら、[現在の環境をTeams評価します](upgrade-plan-journey-evaluate-environment.md)。