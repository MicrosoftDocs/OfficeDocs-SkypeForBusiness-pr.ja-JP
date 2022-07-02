---
title: Teams Only モードの考慮事項
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理は、Microsoft Teams 管理センターで Microsoft Teams のみモードにアップグレードする準備をする方法について説明します。
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
ms.openlocfilehash: b80a563d6d3938a597e57aab4ac93e41df976d32
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605866"
---
# <a name="teams-only-mode-considerations"></a>Teams Only モードの考慮事項

Microsoft 365 またはOffice 365組織の管理者は、個々のユーザーまたはテナント全体を Teams のみモードにアップグレードできます。  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Teams のみモードにアップグレードすると、1 つのクライアント エクスペリエンスを通じて、Microsoft Teams、Microsoft 365 またはOffice 365のチームワークのハブである Microsoft Teams の完全な利点がユーザーに提供されます。 Teams のみモードのユーザーは、送信者がSkype for Businessまたは Teams を使用しているかどうかに関係なく、Teams のすべての通話とチャットを受け取り、相互運用とフェデレーションのサポートの恩恵を受けます。

何千もの顧客が Microsoft Teams に正常にアップグレードされましたが、その過程で組織のアップグレード タイムラインとユーザー エクスペリエンスに影響を与える可能性のある考慮事項があります。 最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。 

> [!IMPORTANT]
> アップグレード計画を開始する場合は、 [Microsoft Teams のアップグレード](upgrade-start-here.md) ガイドの概要を確認してください。 

**共存に関する考慮事項**: Skype for Business Online やSkype for Business Serverを既に使用している組織は、ニーズに合ったペースで Teams を環境に導入できます。 組織は必要に応じて Teams を目的のユーザー セットに段階的にロールアウトでき、Teams を使用するユーザーはSkype for Businessを使用するユーザーと通信できます。また、その逆も可能です。 このエクスペリエンスを管理するために、管理者は共存モードを使用します。このモードでは、エンド ユーザー のクライアント エクスペリエンス、着信チャットと通話のルーティング動作、Teams またはSkype for Businessで新しい会議をスケジュールするかどうかが定義されます。 ユーザーが **Teams のみ** にアップグレードされている場合、ユーザーは他の組織のユーザーとフェデレーションできます。ただし、両方のユーザーが Teams を使用する場合は、最適なエクスペリエンスが提供されます。 Teams のみにアップグレードされたユーザーは、引き続きSkype for Business会議に参加できます。 

> [!IMPORTANT]
> 共存の詳細については、「[Microsoft Teams について理解し、共存と相互運用性をSkype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)する」を参照してください。 Teams と Skype (コンシューマー) の詳細については、「 [Teams と Skype の相互運用性](teams-skype-interop.md)」を参照してください。


**ユーザー固有の考慮事項**: 一部のユーザー シナリオはまだ進化しており、管理者は組織内の他のユーザーをアップグレードするときに、特定のユーザーのアップグレードを一時的に延期することに決める場合があります。 特に、プライマリ デバイスが VDI ベースのユーザーのシナリオへの対処に取り組んでいます。 サイトのお知らせについては、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を監視してください。

> [!NOTE]
> Teams のみモードに移行する前に、Teams をサポートしていないデバイスを交換または更新する必要があります。 

> [!IMPORTANT]
> **注意**: Teams への移行は、技術的な移行以上の作業です。 アップグレードが成功すると、技術的な準備とエンドユーザーの準備の両方が評価されます。 Teams へのアップグレードの実装を計画する方法の詳細については、Teams の[アップグレードガイダンス](upgrade-framework.md)に対するSkype for Businessを確認してください。  
