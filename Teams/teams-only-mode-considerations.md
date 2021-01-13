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
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802377"
---
# <a name="teams-only-mode-considerations"></a>Teams Only モードの考慮事項

Microsoft 365 または Office 365 組織の管理者の場合、Microsoft Teams 管理センターで Teams のみモードにアップグレードするオプションが表示されます。 この機能を使用すると、個々のユーザー、またはテナント全体をアップグレードできます。  

Teams のみモードにアップグレードすると、単一のクライアント エクスペリエンスを介して Microsoft 365 または Office 365 のチームワークのハブである Microsoft Teams の完全な利点がユーザーに提供されます。 さらに、Teams Only モードのユーザーは、送信者が Skype for Business または Teams を使用しているかどうかに関係なく、Teams のすべての通話とチャットを受信し、相互運用とフェデレーションのサポートを利用できます。

何千ものユーザーが Microsoft Teams へのアップグレードに成功している間、組織のアップグレード タイムラインとユーザー エクスペリエンスに影響を与える可能性がある考慮事項があります。 特に、アップグレードするオプションを選択しても、必ずしも組織がこの変更の準備ができているとは限りません。 最高のユーザー エクスペリエンスを得るために、Teams が自分たちの共同作業や通信の要件に適合してることを確認し、確実にお使いのネットワークが Teams をサポートする状態を整えて、ユーザーの準備状態計画を実施してから Teams へのユーザーのアップグレードを実行してください。 

> [!IMPORTANT]
> アップグレード計画を開始する場合は、Microsoft Teams アップグレード ガイドの使用を開始する [方法を確認](upgrade-start-here.md) してください。 

**共存に関** する考慮事項: Skype for Business Online または Skype for Business Server を既に使用している組織は、自分のニーズに合ったペースで Teams を環境に導入できます。 組織は必要に応じて、Teams を目的のユーザー セットに段階的に展開でき、Teams を使用するユーザーは Skype for Business を使用するユーザーと通信でき、その逆も可能です。 このエクスペリエンスを管理するために、管理者は共存モードを使用します。このモードでは、エンド ユーザー のクライアント エクスペリエンス、着信チャットと通話のルーティング動作、および新しい会議が Teams または Skype for Business でスケジュールされるかどうかが定義されます。 ユーザーが Teams にのみアップグレードされた場合、ユーザーは他の組織のユーザーと **フェデレーションできます**。ただし、両方のユーザーが Teams を使用する場合に最適なエクスペリエンスが提供されます。 Teams にのみアップグレードされたユーザーは、引き続き Skype for Business 会議に参加できます。 

> [!IMPORTANT]
> 共存の詳細については [、「Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md)と Skype for Business の共存と相互運用性について」を参照してください。 Teams と Skype (コンシューマー) の詳細については、Teams と Skype の相互運用 [性を参照してください](teams-skype-interop.md)。

**テナント全体の考慮事項**: 次の環境で Teams を有効にするための取り組みです。ただし、現在のところ、Skype for Business テナントが次のいずれかの環境でホストされている場合、管理者は組織内のユーザーをアップグレードしないでください。

 - Office 365 (21Vianet が運営)
 - Office 365 Germany
 - Skype for Business テナントは韓国で **ホストされ、** 組織では Teams データを韓国に保存する必要があります。 現在、Teams にアップグレードする Skype for Business データが韓国に保存されている組織は、Teams データを韓国のデータセンター領域ではなく、アジア データセンター地域に保存します。

**ユーザー固有の** 考慮事項: 一部のユーザー シナリオは引き続き進化しており、管理者は組織内の他のユーザーをアップグレードする際に、特定のユーザーのアップグレードを一時的に延期する場合があります。 特に、プライマリ デバイスが VDI ベースのユーザー向けシナリオの対応に引き続き取り組み中です。 お知らせ [については、Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) サイトを監視してください。

> [!NOTE]
> Teams のみモードに移行する前に、Teams をサポートしないデバイスを交換または更新する必要があります。 

> [!IMPORTANT]
> **注意**: Teams への移行は、技術的な移行以上の機能です。 アップグレードが成功すると、技術的な準備とエンド ユーザーの準備の両方が評価されます。 Teams へのアップグレードの実装の計画の詳細については、Skype for Business から [Teams](upgrade-framework.md) へのアップグレードに関するガイダンスを参照してください。  
