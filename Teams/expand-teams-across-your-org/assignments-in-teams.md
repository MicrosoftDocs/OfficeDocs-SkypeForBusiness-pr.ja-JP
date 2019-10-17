---
title: Teams での割り当て
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 教育担当の Teams で Microsoft Teams 管理センターの課題を管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91d74a96cedcd0cdbdfd6b7fcc5ac1b8e261027e
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547281"
---
# <a name="assignments-in-teams-for-education"></a>教育機関向けの Teams の課題 

割り当ては、学生またはチームメンバーに対して、調査の一環として、クラス内で割り当てられているタスクまたは作業単位数です。 Teams クラス内で課題を作成することができます。

[割り当てについて](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでの課題

Microsoft Teams 管理センターの管理設定を使用すると、組織内の学生と教師が、次の機能をオンまたはオフにできるようにすることができます。 課題に関連する設定を次に示します。

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>1週間のガーディアンメールダイジェスト
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

ガーディアンのメールは、学生の両親またはガーディアンに対して毎週メールで送信されます。 このメールには、前週と来週の課題に関する情報が含まれており、週末に送信されます。 学校のデータ同期機能を使用して、管理者がメールを更新する必要があります。

この設定は、既定ではオフになっています。

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode はブロックベースのコーディングプラットフォームであり、すべての学生に対してコンピューターの科学を実現します。 

これは、サードパーティの製品またはサービスであり、独自の用語とプライバシーポリシーの適用対象となります。 お客様は、サードパーティの製品とサービスの使用に関して責任を負います。

この設定は、既定ではオフになっています。

[MakeCode について、詳細はこちらをご覧ください](https://www.microsoft.com/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Turnitin は、plagiarism の検出サービスです。 これは、サードパーティの製品またはサービスであり、独自の用語とプライバシーポリシーの適用対象となります。 お客様は、サードパーティの製品とサービスの使用に関して責任を負います。

この設定は、既定ではオフになっています。

組織の Turnitin を正常に有効にするには、Turnitin サブスクリプションが既に存在している必要があります。 次の追加情報を入力する必要があります。これは、Turnitin 管理コンソールにあります。

  * _TurnitinApiKey_: この32文字の GUID は、[統合] の下の管理コンソールにあります。
  * _TurnitinApiUrl_: これは、Turnitin 管理コンソールの HTTPS URL です。

この情報を取得するための手順をいくつか紹介します。

TurnitinApiUrl は、管理コンソールのホストアドレスです。
次. `https://your-tenant-name.turnitin.com`

管理コンソールでは、統合と関連付けられた API キーを作成できます。

サイド**メニューから [統合] を選択**し、[**統合の追加**] を選択して、統合の名前を指定します。
![新しい統合の追加を示すスクリーンショット](./educationImages/Assignments_mopo_turnitin2.png)

プロンプトが表示された後、TurnitinApiKey が提供されます。 API キーをコピーして、Microsoft Teams 管理センターに貼り付けます。  これは、キーを表示できる唯一の時間です。
![API キーのコピーを示すスクリーンショット](./educationImages/Assignments_mopo_turnitin3.png)

この設定については、管理センターの [**保存**] ボタンをクリックすると、これらの設定が有効になるまで最大24時間許可してください。

Teams で Turnitin 統合の使用を開始する準備ができましたか? [以前のアクセスプログラム](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)にサインアップします。
