---
title: アプリケーションにアップグレードするための前提条件と環境Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: このガイダンスを使用して、組織にデプロイするための前提条件と環境Teams確認します。
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
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282164"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>アプリケーションの前提条件と環境Teams

![技術準備段階が協調表示されたアップグレード行程図](media/upgrade-banner-tech-readiness.png "技術準備段階が強調表示された、アップグレード行程の各段階")

この記事は、ユーザーの準備段階と並行して実行されるアクティビティである、アップグレードが行われる技術準備段階の一部です。 先に進む前に、前のステージからこれらのアクティビティを完了してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](./upgrade-define-project-scope.md)
- [Skype for Business と Teams の共存と相互運用を理解した](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [アップグレードの手順を選択した](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams複数のサービスとMicrosoft 365サービスOffice 365組み合わせ、そのため、これらのサービスの適切な実装と操作に依存します。 これらのサービスには、SharePoint Online、Exchange Online、および OneDrive for Business が含まれます。

すべてのサービスが必要な場合は、すべて実装することを強くお勧めします。 特定のサービスを実装しない場合、組織に提供できる機能Teams影響します。 たとえば、SharePoint Online を実装する必要はありません。Teams はグループ会話でのファイル共有などの特定の機能を SharePoint Online に依存します。そのため、このサービスを実装しない場合、クライアントを通じて提供される機能が低下します。

前提条件と、他のテクノロジとやり取りTeamsについては、次の記事を参照してください。

- 組織がワークロードに対してデプロイされていない場合Microsoft 365またはOffice 365を開始する」[を参照してください](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

- 組織がドメインまたはドメインの検証済みドメインを追加または構成Microsoft 365場合Office 365、「ドメインに関する[FAQ」を参照してください](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

- 組織が ID を同期して id を同期Azure Active Directory、ID モデルと認証に関するページ[をMicrosoft Teams。](identify-models-authentication.md)

- 組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](Exchange-Teams-interact.md)」をご覧ください。

- 組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)」をご覧ください。

- グループとグループ[のMicrosoft 365やり取りMicrosoft Teams詳細については、 を参照してください](Office-365-groups.md)。

- 組織が教育機関であり、学生情報システムを使用している場合は、「Microsoft[](/schooldatasync)学校データ同期 へようこそ」を参照Microsoft Teams。

- 組織で公衆交換電話網 (PSTN) 通話オプションを検討している場合は、「音声[- 電話システム](cloud-voice-landing-page.md)と PSTN[](calling-plan-landing-page.md)接続」を参照してください。また、どの通話プランが最適か、および直接ルーティングに関するページ電話システム[参照してください](direct-routing-landing-page.md)。

- アプリケーションを展開する前に、すべてのネットワーク要件が確実に満たTeams、「組織のネットワークを準備する」[を参照Microsoft Teams。](prepare-network.md)

- 現在、Skype for Business Online Connector を使用してサービスを管理している場合は、Teams PowerShell モジュールに移動し、既存の PowerShell スクリプトを更新する必要があります。 詳細[については、「Skype for Business Online Connector から powerShell モジュールTeamsに移動する」](teams-powershell-move-from-sfbo.md)を参照してください。

環境が該当する前提条件を満たしていることを確認した後、現在の環境を評価して、 を[Teams。](upgrade-plan-journey-evaluate-environment.md)