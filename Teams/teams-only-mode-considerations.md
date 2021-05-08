---
title: Teams Only モードの考慮事項
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理者は、管理センターで [Microsoft Teamsのみ] モードへのアップグレードを準備Microsoft Teams確認できます。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2232d4774a31f3b081b2410371a5903debe9123
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239014"
---
# <a name="teams-only-mode-considerations"></a>Teams Only モードの考慮事項

組織のMicrosoft 365またはOffice 365管理者は、個々のユーザーまたはテナント全体を [のみ] Teamsアップグレードできます。  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Teams のみモードにアップグレードすると、Microsoft 365 または Office 365 のチームワークのハブである Microsoft Teams の完全な利点を、1 つのクライアント エクスペリエンスで利用できます。 Teams のみモードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかに関係なく、Teams ですべての通話とチャットを受信し、相互運用とフェデレーションのサポートを利用できます。

何千もの顧客が Microsoft Teams に正常にアップグレードされましたが、組織のアップグレード タイムラインとユーザー エクスペリエンスに影響を与える可能性がある考慮事項があります。 最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。 

> [!IMPORTANT]
> アップグレード計画を開始し始めたばかりの場合は、アップグレードの開始に関するガイドをMicrosoft Teams[してください](upgrade-start-here.md)。 

**共存に関** する考慮事項: Skype for Business Online や Skype for Business Server を既に使用している組織は、Teams をニーズに合ったペースで環境に導入できます。 組織は必要に応じて Teams を目的のユーザー セットに段階的にロールアウトでき、Teams を使用するユーザーは Skype for Business を使用するユーザーと通信できます。その逆も可能です。 このエクスペリエンスを管理するために、管理者は共存モードを使用して、エンド ユーザーのクライアント エクスペリエンス、着信チャットと通話のルーティング動作、および新しい会議が Teams または Skype for Business でスケジュールされるかどうかを定義します。 ユーザーが [のみ] にアップグレードされている場合、ユーザーは他の組織の **Teamsできます**。ただし、両方のユーザーがアプリを使用する場合に最適なTeams。 [会議のみ] にアップグレードTeamsユーザーは、引き続き会議Skype for Businessできます。 

> [!IMPORTANT]
> 共存の詳細については、「共存と相互運用性[Microsoft Teams Skype for Businessを参照してください](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。 Teams と Skype (Consumer) の詳細については、「TeamsとSkype[参照してください](teams-skype-interop.md)。


**ユーザー固有の** 考慮事項: 一部のユーザー シナリオはまだ進化しており、管理者は組織内の他のユーザーをアップグレードする際に、特定のユーザーのアップグレードを一時的に延期する場合があります。 特に、プライマリ デバイスが VDI ベースのユーザーのシナリオへの対応に引き続き取り組み中です。 サイトのお知らせについては、「ロードマップ[」をMicrosoft 365してください](https://www.microsoft.com/microsoft-365/roadmap)。

> [!NOTE]
> [移行のみ] Teamsする前に、アプリケーションをサポートしないデバイスを交換または更新する必要Teams。 

> [!IMPORTANT]
> **注意**: この移行へのTeamsは、技術的な移行以上の作業です。 アップグレードが成功すると、技術的な準備とエンドユーザーの準備の両方が評価されます。 アップグレードへのSkype for Businessの[Teams計画の](upgrade-framework.md)詳細については、アップグレードガイダンスを参照Teams。  
