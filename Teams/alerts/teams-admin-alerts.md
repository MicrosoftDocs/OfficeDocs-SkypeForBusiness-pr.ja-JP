---
title: Microsoft Teams の監視とアラート
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで利用できる Teams のアラートと通知の機能について説明します。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 452bcbebeffa3936b9d05270626e11923caf5cda
ms.sourcegitcommit: 72b6f7ab2a44dec395622bfe64119a48094960bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "67283088"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Microsoft Teams の監視とアラート

Microsoft Teams の新しい監視機能とアラート機能は、Teams 管理センターで利用できます。 Teams 管理センターの **[通知&アラート** ] セクションで使用できるさまざまなルール セットを使用して、Teams の機能を監視し、アラートを受信します。 たとえば、IP Phone、コラボレーション バーなどの Teams デバイスが予期せずオフラインになる場合は、Teams デバイスの正常性を積極的に監視できます。  

組織では、Teams の監視とアラートを使用して、次の項目を実行できます。

- Teams の機能を自動的に管理する
- 予期しない内容が表示された場合は、アラートを受け取る必要があります。
- 修正アクションを実行して、物事を軌道に乗り出します。

> [!NOTE]
> Teams 管理センター内のアラート機能は、GCC/GCC-High 環境では使用できません。

## <a name="how-to-manage-monitoring-and-alerting"></a>監視とアラートを管理する方法

 アラート ルールを構成するには、Microsoft 365 のグローバル管理者または Teams サービス管理者である必要があります。 [Teams 管理者ロール](../using-admin-roles.md)と、各管理者ロールがアクセスできるレポートの詳細については、「Teams 管理者ロールを使用して Teams を管理する」を参照してください。

1. Teams 管理センターにサインインします。
2. 左側のナビゲーションで、[ **通知&アラート**] を選択します。
3. [ルール] から構成するルールを選択 **します**。

## <a name="teams-monitoring-rules-reference"></a>Teams 監視ルールリファレンス

引き続き、さまざまな監視機能と構成機能を追加することで、Teams の監視エクスペリエンスの追加と改善を行います。 Teams 管理センターで現在使用できる Teams 監視ルールの一覧を次に示します。


|ルール  |監視機能|監視対象は何ですか? |
|---------|---------|---------|
|アプリの申請  |Teams アプリ | Teams アプリが承認のために送信された場合は、積極的に監視します。|
|[デバイスの状態ルール](device-health-status.md)  |Teams デバイス | オフラインになると、Teams デバイスを積極的に監視できます。|
