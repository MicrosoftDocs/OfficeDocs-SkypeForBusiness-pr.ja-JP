---
title: ユーザーとの通信Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: ラーニング(これは M365 通信コンプライアンス機能の一部です) から、Microsoft Teams の観点から、Insider リスク ソリューション セットの一部である通信コンプライアンスについて説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33a2f72307b82fa4264f264e0f98a4d0aed45ae4
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592842"
---
# <a name="communication-compliance-with-microsoft-teams"></a>ユーザーとの通信Microsoft Teams

コミュニケーション コンプライアンスは、組織内の不適切なメッセージの検出、キャプチャ、および操作を支援することで、コミュニケーション リスクを最小限に抑えるために役立つ Microsoft 365 の Insider リスク ソリューションです。

通信Microsoft Teams、Teams チャネル、プライベート Teams チャネル、または [](/microsoft-365/compliance/communication-compliance-feature-reference) 1:1 およびグループ チャットで、次の種類の不適切なコンテンツを識別するのに役立ちます。

- 不快な言葉、不適切な言葉、嫌がらせをする言葉
- 成人向け、人種差別的な画像、およびゴリー 画像
- 機密情報の共有

通信コンプライアンスと組織のポリシーを構成する方法の詳細については、「組織のコミュニケーション コンプライアンス」を[Microsoft 365](/microsoft-365/compliance/communication-compliance)。 通信コンプライアンスを含Microsoft 365の詳細については、「Insider リスク ソリューション[」を参照してください](/microsoft-365/compliance/insider-risk-solution-overview#communication-compliance)。

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Microsoft Teams で通信コンプライアンスを使用するMicrosoft Teams

コミュニケーションコンプライアンスとMicrosoft Teams緊密に統合され、組織内の通信リスクを最小限に抑えるのに役立ちます。 最初の通信コンプライアンス ポリシーを構成した後は、アラートで自動的にフラグが設定されたメッセージMicrosoft Teams不適切なメッセージやコンテンツを積極的に管理できます。

### <a name="getting-started"></a>はじめに

Microsoft Teams でのコミュニケーション コンプライアンスの開始は、Teams チャネルまたは 1:1 [](/microsoft-365/compliance/communication-compliance-plan) およびグループで不適切なユーザー アクティビティを識別するための定義済みポリシーまたはカスタム ポリシーの計画と作成から始まります。 構成プロセスの一環として、いくつかのアクセス[](/microsoft-365/compliance/communication-compliance-configure)許可と基本的な前提条件を構成する必要があります。

Teams管理者は、次のレベルで通信コンプライアンス ポリシーを構成できます。

- **ユーザー レベル**: このレベルのポリシーは、個々のユーザーにTeams適用するか、組織内のすべてのユーザーにTeams適用できます。 これらのポリシーは、これらのユーザーが 1 対 1 またはグループ チャットで送信できるメッセージをカバーします。 ユーザーのチャット通信は、ユーザーがメンバーであるすべてのMicrosoft Teams自動的に監視されます。
- **Teamsレベル**: このレベルのポリシーは、プライベート チャネルをMicrosoft Teamsチャネルに適用されます。 これらのポリシーは、チャネル内で送信Teamsに適用されます。

### <a name="report-a-concern-in-microsoft-teams"></a>問題を報告するMicrosoft Teams

*Teams メッセージ* の [懸念事項を報告する] オプションは既定で有効であり、Teams 管理センターの Teams メッセージング ポリシー [を使用して制御できます](/microsoftteams/manage-teams-in-modern-portal)。 これにより、組織内のユーザーは、ポリシーのコミュニケーション コンプライアンス レビュー担当者によるレビューのために不適切なメッセージを送信できます。 通信コンプライアンスでのユーザー報告メッセージの詳細については、「通信コンプライアンス ポリシー [」を参照してください](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy)。

![懸念事項の報告メニュー。](./media/communication-compliance-report-a-concern-full-menu.png)

レビューのためにメッセージを送信した後、ユーザーはレビューで提出の確認をMicrosoft Teams。 チャット内の他の参加者には、この通知は表示されない。

![懸念事項の確認を報告します。](./media/communication-compliance-report-a-concern.png)

カスタム ポリシーを作成して割り当てない限り、組織内のユーザーはグローバル ポリシーを自動的に取得します。 グローバル ポリシーの設定を編集するか、1 つ以上のカスタム ポリシーを作成して割り当て、この機能を有効またはオフにします。 詳細については、「Manage [messaging policies in Teams」を参照してください](/microsoftteams/messaging-policies-in-teams)。

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>メッセージ内の不適切なメッセージにMicrosoft Teams

ポリシーを構成し、Microsoft Teams メッセージの通信コンプライアンス アラートを受け取った後は、組織内のコンプライアンスレビュー担当者がこれらのメッセージに対して対応する必要があります。 また、組織で有効になっている場合は、ユーザーから報告されたメッセージも含まれます。 レビュー担当者は、通信コンプライアンスの警告を確認し、メッセージの表示からフラグ付きメッセージを削除することで、組織を保護Microsoft Teams。

![メッセージを削除Teams。](./media/communication-compliance-remove-teams-message.png)

削除されたメッセージとコンテンツは、メッセージまたはコンテンツが削除され、削除に適用できるポリシーを説明する閲覧者向け通知に置き換えられる。 削除されたメッセージまたはコンテンツの送信者にも、削除の状態が通知され、削除に関連するコンテキストの元のメッセージ コンテンツが提供されます。 送信者は、メッセージの削除に適用される特定のポリシー条件を表示できます。

送信者によって表示されるポリシー ヒントの例:

![送信者のポリシー ヒント。](./media/communication-compliance-warning-1.png)

送信者に表示されるポリシー通知の例:

![送信者のポリシー条件情報。](./media/communication-compliance-warning-2.png)

受信者が表示するポリシー ヒントの例:

![受信者のポリシー ヒント。](./media/communication-compliance-warning-3.png)