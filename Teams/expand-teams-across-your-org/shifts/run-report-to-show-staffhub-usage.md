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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49091f7d8ada565adea61bf8219c6da828358893
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569665"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a>レポートを実行してアクティブな StaffHub の使用状況を表示する

> [!IMPORTANT]
> 2019年12月31日有効な場合、Microsoft StaffHub は廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 StaffHub は、2019年12月31日にすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順を使用してレポートを実行し、組織内のアクティブな StaffHub ユーザーの一覧を取得します。 この情報は[、StaffHub teams を Microsoft teams に移行](move-staffhub-teams-to-shifts-in-teams.md)するときに役立つ場合があります。 このレポートでは、StaffHub から Teams への切り替えを行うときに、通信に含める必要があるユーザーを確認できます。

この記事の手順を実行するには、Azure AD Premium が必要です。

1. Azure ポータルにサインインします。
2. 左側のウィンドウで、 **Azure Active Directory**リソースをクリックします。
3. [**監視**] で [**サインイン**] をクリックします。
4. [**アプリケーション**] の下に「 **Microsoft StaffHub**」と入力します。
5. レポートに必要な日付の範囲を設定して、[**適用**] をクリックします。 

    ![アクティブな StaffHub の利用状況を表示する手順を示すスクリーンショット](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a>関連項目

- [Microsoft Teams で Microsoft StaffHub teams をシフトに移行する](move-staffhub-teams-to-shifts-in-teams.md)
