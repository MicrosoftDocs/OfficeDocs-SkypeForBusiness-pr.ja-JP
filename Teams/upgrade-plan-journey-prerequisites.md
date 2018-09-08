---
title: 前提条件とマイクロソフトのチーム - マイクロソフトのチーム環境の依存関係
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: このガイドを使用して、前提条件、およびチームを組織に展開する環境の依存関係について説明するには
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b798ae43d7a47543c78ca38a696a2368413539d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887508"
---
![技術的な準備段階に重点を置いて、旅アップグレードの段階](media/upgrade-banner-tech-readiness.png "技術的な準備段階に重点を置いて、旅アップグレードの段階")

この資料は、ユーザーの準備段階と並行して、完了したアクティビティ、アップグレード、旅の技術的な準備段階の一部です。 次に進む前に前の段階からこれらの活動を完了していることを確認します。

-   [プロジェクトの利害関係者が参加しています。](upgrade-enlist-stakeholders.md)
-   [プロジェクト スコープの定義](https://aka.ms/SkypetoTeams-Scope)
-   [ビジネスとチームの共存と Skype の相互運用性を理解します。](https://aka.ms/SkypeToTeams-Coexist)
-   [アップグレード、旅を選択](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>前提条件とチームの環境の依存関係

チームは、複数の Office 365 サービスを結合しは、適切な実装とこれらのサービスの操作に依存するため。 これらのサービスが含まれます: だけではありませんが、-Exchange Online では、SharePoint Online およびビジネスのための OneDrive です。

必要なすべてのサービスが、それらのすべてを実装することを強くお勧めします。 特定のサービスを導入していない場合は、チームが、組織を提供する機能を影響します。 など、SharePoint Online を実装する必要はありませんがチームに依存して SharePoint Online の特定の機能など、このサービスを実装しないため、グループの会話でのファイル共有のによって提供される機能が減少しますクライアントです。

前提条件、およびチームが他の技術とどのように対話する方法について説明する以下の資料を参照してください。

-   組織では、任意の Office 365 のワークロードを展開していない場合、は、[ビジネス向けの Office 365 の概要](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)を参照してください。

-   組織は、追加や、検証済みのドメインを Office 365 用に構成されていない場合、は[、Office 365 のドメインの確認](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)を参照してください。

-   組織が Azure Active Directory にユーザーを同期していない場合は、[識別情報モデルとマイクロソフトのチームでの認証](identify-models-authentication.md)を参照してください。

-   組織 doesn¹t は、Exchange オンライン場合は、 [Exchange および Microsoft のチームがやり取りする方法を理解する](Exchange-Teams-interact.md)を参照してください。

-   組織は、SharePoint Online に割り当てられていない、 [SharePoint Online およびビジネスのための OneDrive がマイクロソフトのチームとどのようにやり取りする方法を理解する](SharePoint-OneDrive-interact.md)を参照してください。

-   学習方法[Office 365 のグループとマイクロソフトのチームが対話します](Office-365-groups.md)。

-   組織は、教育機関、学生情報システムでは、マイクロソフトのチームを展開する前に[学校のデータの同期を展開する](https://docs.microsoft.com/schooldatasync)に使用する場合。
                                                                           

ことの確認、環境がすべて該当する場合の前提条件、[チームの現在の環境の評価](upgrade-plan-journey-evaluate-environment.md)を満たしています。