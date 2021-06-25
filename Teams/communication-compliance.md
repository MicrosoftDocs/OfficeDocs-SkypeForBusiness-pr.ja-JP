---
title: ユーザーとの通信Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: ラーニング(これは M365 通信コンプライアンス機能の一部) の観点から、insider リスク ソリューション セットの一部である通信コンプライアンスについて説明します (Microsoft Teams)。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5957e8900a9b3d9915a88e3ad8bf5e18c7a08b3
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126903"
---
# <a name="communication-compliance-with-microsoft-teams"></a>ユーザーとの通信Microsoft Teams

コミュニケーション コンプライアンスは、組織内の不適切なメッセージの検出、キャプチャ、および操作を支援することで、通信リスクを最小限に抑えるために役立つ Microsoft 365 の Insider リスク ソリューションです。

通信Microsoft Teams、Teams チャネル、プライベート Teams[](/microsoft-365/compliance/communication-compliance-feature-reference)チャネル、または 1:1 およびグループ チャットで、次の種類の不適切なコンテンツを識別するのに役立ちます。

- 不快な言葉、不適切な言葉、嫌がらせをする言葉
- 成人向け、人種差別的な画像、およびゴリー 画像
- 機密情報の共有

通信コンプライアンスと組織のポリシーを構成する方法の詳細については、「組織の通信コンプライアンス」を[Microsoft 365。](/microsoft-365/compliance/communication-compliance)

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Microsoft Teams で通信コンプライアンスを使用するMicrosoft Teams

通信コンプライアンスとMicrosoft Teamsは緊密に統合され、組織内の通信リスクを最小限に抑えるのに役立ちます。 最初の通信コンプライアンス ポリシーを構成した後は、アラートで自動的にフラグが設定されたメッセージMicrosoft Teams不適切なメッセージやコンテンツを積極的に管理できます。

### <a name="getting-started"></a>はじめに

Microsoft Teams でのコミュニケーション コンプライアンスの開始は、Teams チャネルまたは[](/microsoft-365/compliance/communication-compliance-plan)1:1 およびグループで不適切なユーザー アクティビティを識別する定義済みポリシーまたはカスタム ポリシーの計画と作成から始まります。 構成プロセスの一環として、いくつかのアクセス[](/microsoft-365/compliance/communication-compliance-configure)許可と基本的な前提条件を構成する必要があります。

Teams管理者は、次のレベルで通信コンプライアンス ポリシーを構成できます。

- **ユーザー レベル**: このレベルのポリシーは、個々のユーザー Teams適用するか、組織内のすべてのユーザー Teamsに適用できます。 これらのポリシーは、これらのユーザーが 1 対 1 またはグループ チャットで送信できるメッセージをカバーします。 ユーザーのチャット通信は、ユーザーがメンバーであるすべてのMicrosoft Teams自動的に監視されます。
- **Teams レベル**: このレベルのポリシーは、プライベート チャネルを含む Microsoft チーム チャネルに適用されます。 これらのポリシーは、チャネル内で送信されたTeamsのみをカバーします。

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>メッセージ内の不適切なメッセージにMicrosoft Teams

ポリシーを構成し、Microsoft Teams メッセージの通信コンプライアンス アラートを受け取った後は、組織内のコンプライアンスレビュー担当者がこれらのメッセージに対してアクションを実行します。 レビュー担当者は、コミュニケーション コンプライアンスの警告を確認し、フラグ付きメッセージをグループ内のビューから削除することで、組織を保護Microsoft Teams。

![メッセージを削除Teams](./media/communication-compliance-remove-teams-message.png)

削除されたメッセージとコンテンツは、メッセージまたはコンテンツが削除され、削除に適用できるポリシーを説明する閲覧者向け通知に置き換えられる。 削除されたメッセージまたはコンテンツの送信者にも、削除の状態が通知され、削除に関連するコンテキストの元のメッセージ コンテンツが提供されます。 送信者は、メッセージの削除に適用される特定のポリシー条件を表示できます。

送信者によって表示されるポリシー ヒントの例:

![送信者のポリシー ヒント](./media/communication-compliance-warning-1.png)

送信者に表示されるポリシー条件通知の例:

![送信者のポリシー条件情報](./media/communication-compliance-warning-2.png)

受信者が表示するポリシー ヒントの例:

![受信者のポリシー ヒント](./media/communication-compliance-warning-3.png)