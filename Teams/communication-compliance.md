---
title: Microsoft Teams への通信のコンプライアンス
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: コミュニケーションのコンプライアンスについては、「Microsoft Teams の観点からの insider リスクソリューションセットの一部 (M365 通信のコンプライアンス機能の一部)」をご覧ください。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328256"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Microsoft Teams への通信のコンプライアンス

通信のコンプライアンスは、Microsoft 365 の insider のリスクソリューションであり、組織内の不適切なメッセージの検出、キャプチャ、および操作を支援することで、コミュニケーションのリスクを最小限に抑えることができます。

Microsoft Teams では、コミュニケーションのコンプライアンスは、チームチャネルまたは1:1 およびグループチャットで [次の種類](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) の不適切なコンテンツを特定するのに役立ちます。

- 不快感を持つ、欠い、嫌がらせの言葉
- アダルト、racy、gory の画像
- 機密情報の共有

通信のコンプライアンスと組織のポリシーの構成方法の詳細については、「 [Microsoft 365 での通信のコンプライアンス](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)」を参照してください。

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Microsoft Teams で通信のコンプライアンスを使用する方法

コミュニケーションのコンプライアンスと Microsoft Teams は密接に統合されており、組織の通信リスクを最小限に抑えることができます。 最初の通信のコンプライアンスポリシーを構成した後は、不適切な Microsoft Teams のメッセージやコンテンツが自動的に通知に表示されるように管理できます。

### <a name="getting-started"></a>はじめに

Microsoft Teams での通信の概要については、「チームチャネルまたは1:1 およびグループで不適切なユーザーのアクティビティを特定するための事前定義済みまたはカスタムポリシーの [計画](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) と作成」をご覧ください。 構成プロセスの一部として、一部の権限と基本的な前提条件を [構成](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) する必要があることに注意してください。

チーム管理者は、次のレベルで通信コンプライアンスポリシーを構成できます。

- **ユーザーレベル**: このレベルのポリシーは、個々の teams ユーザーに適用されるか、組織内のすべての teams ユーザーに適用される可能性があります。 これらのポリシーでは、これらのユーザが1:1 またはグループチャットで送信する可能性のあるメッセージを対象としています。 ユーザーのチャットは、ユーザーがメンバーになっているすべての Microsoft Teams で自動的に監視されます。
- **チームレベル**: このレベルのポリシーは、Microsoft チームチャネルに適用されます。 これらのポリシーには、Teams チャネルでのみ送信されたメッセージが含まれています。

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Microsoft Teams で不適切なメッセージに対処する

ポリシーを構成して、Microsoft Teams メッセージの通信のコンプライアンス警告を受信した後は、組織のコンプライアンスレビュー担当者がこれらのメッセージに対処する時間です。 レビュー担当者は、通信コンプライアンスの警告を確認し、Microsoft Teams のビューからフラグ付きのメッセージを削除することで、組織を保護することができます。

![Teams でメッセージを削除する](./media/communication-compliance-remove-teams-message.png)

削除されたメッセージとコンテンツは、メッセージまたはコンテンツが削除されたこと、および削除に適用できるポリシーを説明する通知に置き換えられます。 削除されたメッセージまたはコンテンツの送信者は、削除の状態についても通知され、削除に関連するコンテキストについて元のメッセージコンテンツが提供されます。 また、送信者は、メッセージの削除に適用される特定のポリシー条件を表示することもできます。

送信者に表示されるポリシーヒントの例:

![送信者のポリシーヒント](./media/communication-compliance-warning-1.png)

送信者に表示されるポリシー条件通知の例:

![送信者のポリシー条件情報](./media/communication-compliance-warning-2.png)

受信者に表示されるポリシーヒントの例:

![受信者のポリシーヒント](./media/communication-compliance-warning-3.png)
