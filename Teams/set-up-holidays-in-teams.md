---
title: Microsoft Teams で休日を設定する
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: 自動応答で使用するMicrosoft Teams で休日を設定する方法について説明します。
ms.openlocfilehash: 6ed508f9060ff6ab5e0fb427c500b9e1cd8a707f
ms.sourcegitcommit: 81b3403a1a77ba202690c2d88bd8d1d5257048e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69379333"
---
# <a name="set-up-holidays-in-microsoft-teams"></a>Microsoft Teams で休日を設定する

Teams 休日機能を使用すると、部門、通話キュー、または組織内のユーザーが異なる勤務時間に従うか、利用できない特定の日付と時刻について、発信者に代替メッセージとルーティングを提供できます。 たとえば、組織が閉じられる可能性がある元旦の休日を作成できます。

ここで作成する休日は、 [自動応答を設定](create-a-phone-system-auto-attendant.md)するときに使用できます。それぞれに独自のあいさつと通話ルーティングの設定があります。

## <a name="create-a-holiday"></a>休日を作成する

休日を作成するには

1. Microsoft Teams 管理センターで、**Voice** > **Holidays** に移動します。

2. [ **新しい休日**] を選択します。

3. 休日の名前を入力します。

4. [ **新しい日付の追加] を選択します**。

5. [ **開始時刻**] で、予定表アイコンを選択し、休日を開始する日付を選択します。

6. ドロップダウン リストを使用して、休日の開始時刻を選択します。

7. [ **終了時刻**] で予定表アイコンを選択し、休日を終了する日付を選択します。

8. ドロップダウン リストを使用して、休日の終了時刻を選択します。 **終了時刻** は、**開始時刻** の後である必要があります。  

   > [!NOTE]
   > 休日が 1 日 (つまり 24 時間) の場合は、 **終了時刻** を次の日に、時刻を午前 12 時に設定する必要があります。 たとえば、組織が元旦の 1 月 1 日に閉じている場合は、 **開始時刻** を 1 月 1 日の午前 12 時 00 分に設定し、[ **終了時刻]** を 1 月 2 日の午前 12 時 00 分に設定します。

9. 必要に応じて、定期的な休日の日付をさらに追加します。 1 回の休日に最大 10 個の個別の日付範囲を追加できます。  

10. **[保存]** を選択します。

    ![日付が 3 年間設定されている休日のユーザー インターフェイスのスクリーンショット。](media/holidays-set-up.png)

## <a name="change-a-holiday"></a>休日を変更する

休日を変更するには

1. Microsoft Teams 管理センターで、**Voice** > **Holidays** に移動します。

2. 一覧から休日を選択します。

3. [ **開始時刻**] で、予定表アイコンを選択し、休日を開始する日付を選択します。

4. ドロップダウン リストを使用して、休日の開始時刻を選択します。

5. [ **終了時刻**] で予定表アイコンを選択し、休日を終了する日付を選択します。 

6. ドロップダウン リストを使用して、休日の終了時刻を選択します。 **終了時刻** は、**開始時刻** の後である必要があります。  

7. **[保存]** を選択します。

## <a name="related-topics"></a>関連項目

[Teams の自動応答と通話キューの計画](plan-auto-attendant-call-queue.md)
