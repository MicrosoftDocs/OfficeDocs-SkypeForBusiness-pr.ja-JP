---
title: Teams Only モードの考慮事項
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理者は、Microsoft Teams 管理センターでMicrosoft Teamsのみモードにアップグレードする準備をする方法について説明します。
ms.localizationpriority: medium
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
ms.openlocfilehash: c8db18a835b5e54043e572400e547c7cd5989b87
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390739"
---
# <a name="teams-only-mode-considerations"></a>Teams Only モードの考慮事項

Microsoft 365またはOffice 365組織の管理者は、個々のユーザーまたはテナント全体をTeamsのみモードにアップグレードできます。  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Teamsのみモードにアップグレードすると、Microsoft 365またはOffice 365のチームワークのハブであるMicrosoft Teamsの完全な利点が 1 つのクライアント エクスペリエンスによってユーザーに提供されます。 Teamsのみモードのユーザーは、送信者がSkype for BusinessまたはTeamsを使用しているかどうかに関係なく、Teamsのすべての通話とチャットを受け取り、相互運用とフェデレーションのサポートの恩恵を受けます。

何千人もの顧客がMicrosoft Teamsに正常にアップグレードされましたが、その過程で組織のアップグレード のタイムラインとユーザー エクスペリエンスに影響を与える可能性のある考慮事項があります。 最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。 

> [!IMPORTANT]
> アップグレード計画を開始したばかりの場合は、Microsoft Teamsアップグレードガイドの概要[を確認してください](upgrade-start-here.md)。 

**共存に関する考慮事項**: Skype for Business Online やSkype for Business Serverを既に使用している組織は、ニーズに合ったペースで環境にTeamsを導入できます。 組織は、必要に応じて目的のユーザー セットにTeamsを段階的にロールアウトでき、Teamsを使用するユーザーはSkype for Businessを使用するユーザーと通信できます。 このエクスペリエンスを管理するために、管理者は共存モードを使用します。このモードでは、エンド ユーザー クライアント エクスペリエンス、着信チャットと通話のルーティング動作、および新しい会議がTeamsまたはSkype for Businessでスケジュールされているかどうかが定義されます。 ユーザーが **Teams のみ** にアップグレードされた場合、ユーザーは他の組織のユーザーとフェデレーションできます。ただし、両方のユーザーがTeamsを使用する場合に最適なエクスペリエンスが提供されます。 Teamsのみにアップグレードされたユーザーは、引き続きSkype for Business会議に参加できます。 

> [!IMPORTANT]
> 共存の詳細については、「[Microsoft TeamsとSkype for Business共存と相互運用性について理解](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」を参照してください。 TeamsとSkype (コンシューマー) の詳細については、[相互運用性のTeamsとSkype](teams-skype-interop.md)に関するページを参照してください。


**ユーザー固有の考慮事項**: 一部のユーザー シナリオはまだ進化しており、管理者は組織内の他のユーザーをアップグレードするときに、特定のユーザーのアップグレードを一時的に延期することに決める場合があります。 特に、プライマリ デバイスが VDI ベースのユーザーのシナリオへの対処に取り組んでいます。 サイトのお知らせについては、[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を監視します。

> [!NOTE]
> Teamsのみモードに移行する前に、Teamsをサポートしていないデバイスを交換または更新する必要があります。 

> [!IMPORTANT]
> **注意**: Teamsへの移行は、技術的な移行以上の作業です。 アップグレードが成功すると、技術的な準備とエンドユーザーの準備の両方が評価されます。 Teamsへのアップグレードの実装の計画の詳細については、[アップグレードガイダンス](upgrade-framework.md)をTeamsするSkype for Businessを確認してください。  
