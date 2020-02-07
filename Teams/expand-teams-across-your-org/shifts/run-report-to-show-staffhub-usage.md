---
title: レポートを実行してアクティブな StaffHub の使用状況を表示する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: レポートを実行して、組織内のアクティブな StaffHub ユーザーの一覧を取得する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe7851e57cd6d812d0b8904668ca5fd67fd5999d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826695"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a>レポートを実行してアクティブな StaffHub の使用状況を表示する

> [!IMPORTANT]
> 2019 年 12 月 31 日より、Microsoft StaffHub が廃止されます。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は、2019 年 12 月 31 日以降すべてのユーザーがご利用できなくなります。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順を使用してレポートを実行し、組織内のアクティブな StaffHub ユーザーの一覧を取得します。 この情報は[、StaffHub teams を Microsoft teams に移行](move-staffhub-teams-to-shifts-in-teams.md)するときに役立つ場合があります。 このレポートでは、StaffHub から Teams への切り替えを行うときに、通信に含める必要があるユーザーを確認できます。

この記事の手順を実行するには、Azure AD Premium が必要です。

1. Azure ポータルにサインインします。
2. 左側のウィンドウで、 **Azure Active Directory**リソースをクリックします。
3. [**監視**] で [**サインイン**] をクリックします。
4. [**アプリケーション**] の下に「 **Microsoft StaffHub**」と入力します。
5. レポートに必要な日付の範囲を設定して、[**適用**] をクリックします。 

    ![アクティブな StaffHub の利用状況を表示する手順を示すスクリーンショット](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a>関連トピック

- [Microsoft StaffHub のチームを Microsoft Teams のシフトに移動する](move-staffhub-teams-to-shifts-in-teams.md)
