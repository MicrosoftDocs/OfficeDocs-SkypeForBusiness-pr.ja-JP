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
description: 教育担当の Teams で Microsoft Teams 管理センターの課題を管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 188f4398136c2939ad2a84d75ab27942a5a4593b
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433432"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

割り当ては、学生またはチームメンバーに対して、調査の一環として、クラス内で割り当てられているタスクまたは作業単位数です。 Teams クラス内で課題を作成することができます。

[割り当てについて](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの課題

Microsoft Teams 管理センターの管理設定を使用すると、組織内の学生と教師が、次の機能をオンまたはオフにできるようにすることができます。 課題に関連する設定を次に示します。

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>1週間のガーディアンメールダイジェスト
ガーディアンのメールは、学生の両親またはガーディアンに対して毎週メールで送信されます。 このメールには、前週と来週の課題に関する情報が含まれており、週末に送信されます。 学校のデータ同期機能を使用して、管理者がメールを更新する必要があります。

この設定は、既定ではオフになっています。

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode はブロックベースのコーディングプラットフォームであり、すべての学生に対してコンピューターの科学を実現します。 

これは、サードパーティの製品またはサービスであり、独自の用語とプライバシーポリシーの適用対象となります。 お客様は、サードパーティの製品とサービスの使用に関して責任を負います。

この設定は、既定ではオフになっています。

[MakeCode について、詳細はこちらをご覧ください](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin は、plagiarism の検出サービスです。 これは、サードパーティの製品またはサービスであり、独自の用語とプライバシーポリシーの適用対象となります。 お客様は、サードパーティの製品とサービスの使用に関して責任を負います。

この設定は、既定ではオフになっています。

組織の Turnitin を正常に有効にするには、Turnitin サブスクリプションが既に存在している必要があります。 次の追加情報を入力する必要があります。これは、Turnitin 管理コンソールにあります。

  * _TurnitinApiKey_: この32文字の GUID は、[統合] の下の管理コンソールにあります。
  * _TurnitinApiUrl_: これは、Turnitin 管理コンソールの HTTPS URL です。

この情報を取得するための手順をいくつか紹介します。

TurnitinApiUrl は、管理コンソールのホストアドレスです。
![ホストアドレスを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin1.png)

[インテグレーション] タブに移動して、統合機能を追加します。
![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

プロンプトが表示された後、TurnitinApiKey が提供されます。 このキーをコピーして、Microsoft Teams 管理センターに貼り付けます。 
![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

[Turnitin と Microsoft Teams の統合の詳細については、こちらを参照してください。](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Turnitin について、詳細はこちらをご覧ください](https://www.turnitin.com/)
