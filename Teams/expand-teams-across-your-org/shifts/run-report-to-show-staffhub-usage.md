---
title: レポートを実行してアクティブな StaffHub の利用状況を表示する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: レポートを実行して、組織内のアクティブな StaffHub ユーザーの一覧を取得する方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59931183cadec09b2fc26a55cf7e284f51198efc
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548208"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a>レポートを実行してアクティブな StaffHub の利用状況を表示する

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。  

この記事の手順を使用してレポートを実行し、組織内のアクティブな StaffHub ユーザーの一覧を取得します。 この情報は[、StaffHub teams を Microsoft teams に移行](move-staffhub-teams-to-shifts-in-teams.md)するときに役立つ場合があります。 このレポートでは、StaffHub から Teams への切り替えを行うときに、通信に含める必要があるユーザーを確認できます。

この記事の手順を実行するには、Azure AD Premium が必要です。

1. Azure ポータルにサインインします。
2. 左側のウィンドウで、 **Azure Active Directory**リソースをクリックします。
3. [**監視**] で [**サインイン**] をクリックします。
4. [**アプリケーション**] の下に「 **Microsoft StaffHub**」と入力します。
5. レポートに必要な日付の範囲を設定して、[**適用**] をクリックします。 

    ![アクティブな StaffHub の利用状況を表示する手順を示すスクリーンショット](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a>関連トピック

- [Microsoft Teams で Microsoft StaffHub teams をシフトに移行する](move-staffhub-teams-to-shifts-in-teams.md)
