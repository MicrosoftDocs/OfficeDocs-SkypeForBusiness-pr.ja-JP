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
description: 管理者は、Microsoft Teams 管理センターで Microsoft Teams のみモードにアップグレードする準備をする方法について説明します。
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
ms.openlocfilehash: 4a38967ffb80f59fab88006b5aad2e6ecb76395c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460997"
---
# <a name="teams-only-mode-considerations"></a>Teams Only モードの考慮事項

Microsoft 365 または 365 Office 365 組織の管理者は、個々のユーザーまたはテナント全体を Teams のみモードにアップグレードできます。  

Teams のみモードにアップグレードすると、単一のクライアント エクスペリエンスで Microsoft 365 または Office 365 のチームワークのハブである Microsoft Teams の利点をフルに利用できます。 Teams のみモードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかに関係なく、Teams ですべての通話とチャットを受信し、相互運用とフェデレーションのサポートを利用できます。

何千ものユーザーが Microsoft Teams へのアップグレードに成功しているが、組織のアップグレード タイムラインとユーザー エクスペリエンスに影響を与える可能性がある考慮事項があります。 最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。 

> [!IMPORTANT]
> アップグレード計画を開始する場合は [、Microsoft Teams](upgrade-start-here.md) アップグレード ガイドの使用を必ず確認してください。 

**共存に関** する考慮事項: Skype for Business Online または Skype for Business Server を既に使用している組織は、自分のニーズに合ったペースで Teams を環境に導入できます。 組織は、必要に応じて Teams を目的のユーザー セットに段階的に展開でき、Teams を使用するユーザーは Skype for Business を使用するユーザーと通信でき、その逆も可能です。 このエクスペリエンスを管理するために、管理者は共存モードを使用します。このモードでは、エンド ユーザー のクライアント エクスペリエンス、着信チャットと通話のルーティング動作、および新しい会議が Teams または Skype for Business でスケジュールされるかどうかが定義されます。 ユーザーが Teams にのみアップグレードされた場合、ユーザーは他の組織のユーザーと **フェデレーションできます**。ただし、両方のユーザーが Teams を使用する場合に最適なエクスペリエンスが提供されます。 Teams にのみアップグレードされたユーザーは、引き続き Skype for Business 会議に参加できます。 

> [!IMPORTANT]
> 共存の詳細については [、「Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md)と Skype for Business の共存と相互運用性について」を参照してください。 Teams と Skype (コンシューマー) の詳細については、Teams と Skype の相互運用 [性を参照してください](teams-skype-interop.md)。


**ユーザー固有の** 考慮事項: 一部のユーザー シナリオは引き続き進化しており、管理者は組織内の他のユーザーをアップグレードする際に、特定のユーザーのアップグレードを一時的に延期する場合があります。 特に、プライマリ デバイスが VDI ベースのユーザー向けシナリオの対応に引き続き取り組み中です。 サイトのお知らせについては [、Microsoft 365 ロードマップを監視してください](https://www.microsoft.com/microsoft-365/roadmap)。

> [!NOTE]
> Teams のみモードに移行する前に、Teams をサポートしないデバイスを交換または更新する必要があります。 

> [!IMPORTANT]
> **注意**: Teams への移行は、技術的な移行以上の機能です。 アップグレードが成功すると、技術的な準備とエンド ユーザーの準備の両方が評価されます。 Teams へのアップグレードの実装の計画の詳細については、Skype for Business から [Teams](upgrade-framework.md) へのアップグレードに関するガイダンスを確認してください。  
