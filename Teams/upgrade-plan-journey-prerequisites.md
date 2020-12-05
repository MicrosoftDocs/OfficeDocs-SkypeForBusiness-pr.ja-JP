---
title: Teams にアップグレードするための前提条件と環境の依存関係
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: このガイダンスを使用して、組織にチームを展開するための前提条件と環境の依存関係について説明します。
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578280"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Teams の前提条件と環境上の依存関係

![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")

この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。 続行する前に、以前のステージでこれらのアクティビティが完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams は、複数の Microsoft 365 と Office 365 サービスを組み合わせたものであり、これらのサービスの適切な実装と運用によって異なります。 これらのサービスには、SharePoint Online、Exchange Online、OneDrive for Business などが含まれますが、これらは限定されません。

すべてのサービスが必要となるわけではありませんが、すべてのサービスを実装することを強くお勧めします。 特定のサービスを実装しない場合は、チームが組織に提供できる機能に影響します。 たとえば、SharePoint Online を実装する必要はありませんが、チームは SharePoint Online を使用して、グループ会話でのファイル共有などの特定の機能を利用しているため、このサービスを実装しないと、クライアントで提供される機能が低下します。

前提条件については、次の記事を参照してください。チームと他のテクノロジとの相互作用について説明します。

- 組織で Microsoft 365 または Office 365 のワークロードを展開していない場合は、「使用を [開始](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)する」を参照してください。

- 組織で、Microsoft 365 または Office 365 の確認済みドメインを追加または構成していない場合は、「ドメインに関する [FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)」を参照してください。

- 組織で id が Azure Active Directory に同期されていない場合は、「 [Microsoft Teams の id モデルと認証](identify-models-authentication.md)」を参照してください。

- 組織に Exchange Online がインストールされていない場合は、「 [exchange と Microsoft Teams の相互作用](Exchange-Teams-interact.md)」を参照してください。

- 組織に SharePoint Online がインストールされていない場合は、「 [Sharepoint online と OneDrive For business が Microsoft Teams とどのように連携するかについ](SharePoint-OneDrive-interact.md)て」を参照してください。

- [Microsoft 365 グループおよび Microsoft Teams の相互作用](Office-365-groups.md)について説明します。

- 組織が教育機関であり、学生の情報システムを使用している場合は、「microsoft Teams を展開する前に [Microsoft School Data Sync へようこそ](https://docs.microsoft.com/schooldatasync) 」を参照してください。

- 公衆交換電話網 (PSTN) の通話オプションを組織で検討している場合は、「 [ボイスフォンシステムと pstn 接続](cloud-voice-landing-page.md)」を参照してください。 [通話プランは適切](calling-plan-landing-page.md)であり、 [電話システムによる直接ルーティング](direct-routing-landing-page.md)が必要です。

- チームをロールアウトする前にすべてのネットワーク要件を満たしていることを確認するには、「 [Microsoft teams 用に組織のネットワークを準備](prepare-network.md)する」を参照してください。

環境が該当するすべての前提条件を満たしていることを確認したら、 [チームの現在の環境を評価](upgrade-plan-journey-evaluate-environment.md)します。
