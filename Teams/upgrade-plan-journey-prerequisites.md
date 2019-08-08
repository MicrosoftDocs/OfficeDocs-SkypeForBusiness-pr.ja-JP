---
title: Microsoft Teams の前提条件 |依存関係の導入のアップグレード
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: このガイダンスを使用して、組織にチームを展開するための前提条件と環境の依存関係について説明します。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0da49178a55cc14b98946beb7212a1627829c13e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236074"
---
![テクニカルレディネスステージを強調したアップグレードの図](media/upgrade-banner-tech-readiness.png "技術的な準備段階に重点を置いたアップグレードの段階")

この記事は、アップグレードが行われる技術準備段階の一部であり、ユーザーの準備段階と並行して実行されるアクティビティです。 続行する前に、以前のステージでこれらのアクティビティが完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Teams の前提条件と環境上の依存関係

Teams では、複数の Office 365 サービスが組み合わされているため、これらのサービスの適切な実装と運用によって異なります。 これらのサービスには、SharePoint Online、Exchange Online、OneDrive for Business などが含まれますが、これらは限定されません。

すべてのサービスが必要となるわけではありませんが、すべてのサービスを実装することを強くお勧めします。 特定のサービスを実装しない場合は、チームが組織に提供できる機能に影響します。 たとえば、SharePoint Online を実装する必要はありませんが、チームは SharePoint Online を使用して、グループ会話でのファイル共有などの特定の機能を利用しているため、このサービスを実装しないと、クライアント.

前提条件については、次の記事を参照してください。チームと他のテクノロジとの相互作用について説明します。

- 組織で Office 365 ワークロードを展開していない場合は、「一般[法人向け office 365](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)の概要」を参照してください。

- 組織で Office 365 の確認済みドメインを追加または構成していない場合は、「 [office 365 ドメインを確認](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)する」を参照してください。

- 組織で id が Azure Active Directory に同期されていない場合は、「 [Microsoft Teams の id モデルと認証](identify-models-authentication.md)」を参照してください。

- 組織に Exchange Online がインストールされていない場合は、「 [exchange と Microsoft Teams の相互作用](Exchange-Teams-interact.md)」を参照してください。

- 組織に SharePoint Online がインストールされていない場合は、「 [Sharepoint online と OneDrive For business が Microsoft Teams とどのように連携するかについ](SharePoint-OneDrive-interact.md)て」を参照してください。

- [Office 365 グループと Microsoft Teams の相互作用](Office-365-groups.md)について説明します。

- 組織が教育機関であり、学生の情報システムを使用している場合は、Microsoft Teams を展開する前に[School Data Sync を展開](https://docs.microsoft.com/schooldatasync)してください。

環境が該当するすべての前提条件を満たしていることを確認したら、[チームの現在の環境を評価](upgrade-plan-journey-evaluate-environment.md)します。
