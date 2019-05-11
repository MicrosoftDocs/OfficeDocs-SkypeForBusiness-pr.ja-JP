---
title: Teams での割り当て
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: 教育のチームでマイクロソフトのチームの管理センターでの割り当てを管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 263b9dda6929bd6956df803a33764634808cddf3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914024"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

割り当ては、タスクまたはその調査の一部としてクラスで受講生受講者またはチーム メンバーに割り当てられた作業時間の単位です。 チーム クラス内での割り当てを作成できます。

[割り当ての詳細を表示します](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>マイクロソフトのチームの管理センターでの割り当て

マイクロソフトのチーム管理センターの管理設定を使用して生徒と教師は、組織内で利用できる次の機能をオンまたはオフにします。 割り当てに関連する設定は、次のように。

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>ガーディアン電子メールの今週のダイジェスト
保護者の e メールは、受講者の親または保護者に送信された電子メールを毎週です。 電子メールおよび今後の週では、前の週からの割り当てに関する情報が含まれ、週末に送信されます。 電子メールは、学校のデータの同期機能を使用して管理者が更新する必要があります。

この設定は既定ではオフです。

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode は、ブロック ・ ベースのコーディング プラットフォームで、すべての受講者用コンピューター サイエンスをもたらしです。 

これは、サード ・ パーティ製品またはサービスは独自の利用規約とプライバシー ポリシーです。 任意のサードパーティ製品およびサービスの使用に責任があります。

この設定は既定ではオフです。

[MakeCode の詳細を表示します](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin は、盗用検出サービスです。 これは、サード ・ パーティ製品またはサービスは独自の利用規約とプライバシー ポリシーです。 任意のサードパーティ製品およびサービスの使用に責任があります。

この設定は既定ではオフです。

組織の Turnitin が正常に有効にするには、Turnitin のサブスクリプションを既に持っている必要があります。 Turnitin 管理者コンソールには次の追加情報を入力する必要があります。

  * _TurnitinApiKey_: これは、管理コンソールの統合] の下に 32 文字の GUID です。
  * _TurnitinApiUrl_: これは、Turnitin 管理者コンソールの HTTPS URL です。

この情報を取得するためのいくつかの手順を次に示します。

TurnitinApiUrl は、管理者コンソールのホスト アドレスです。
![TurnItInApiUrl を検索します。](./educationImages/Assignments_mopo_turnitin1.png)

統合] タブに移動し、統合環境を追加します。
![TurnItInApiUrl を検索します。](./educationImages/Assignments_mopo_turnitin2.png)

画面の指示を実行した後に、TurnitinApiKey が与えられます。 このキーをコピーし、マイクロソフトのチームの管理ページに貼り付けます。 
![TurnItInApiUrl を検索します。](./educationImages/Assignments_mopo_turnitin3.png)

[Turnitin とマイクロソフトのチーム間の統合の詳細を表示します](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Turnitin の詳細を表示します](https://www.turnitin.com/)
