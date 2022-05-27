---
title: マルチテナント監査
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: TRM の監査ログ。
f1keywords: ''
ms.openlocfilehash: 3681f50f0e15a7688a944c14e69907ba53dd2817
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676613"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Teams Rooms マネージド サービスの監査ログ

Teams Roomsマネージド (TRM) サービスの監査では、ユーザーと管理者がポータルで実行したアクティビティの監査レコードを検索できます。 この機能は既定で有効になっています。 マネージド サービス管理者のみが、ログをエクスポートして表示する権限を持ちます。

> [!NOTE]
> TRM サービスで実行されたアクションは、Microsoft 365またはOffice 365監査に記録されません 

## <a name="exporting-logs"></a>ログのエクスポート

監査ログ検索のすべての結果をエクスポートすると、統合監査ログの生データが、ローカル コンピューターにダウンロードされるコンマ区切り値 (CSV) ファイルにコピーされます。 

**ログをダウンロードするには** 

1. **設定 >全般>監査ログ** に移動します。
1. 対象のログの日付範囲を定義するには、 **開始日** と終了日を入力 **します。**

   > [!NOTE]
   > ログは最大 180 日間のみ使用できます。

1. [**ログのダウンロード**] を選択します。

   ![監査ログの日付範囲](../media/multi-tenant-auditing.png)

   ウィンドウの下部に表示されるメッセージで、CSV ファイルを開くか保存するかを確認するメッセージが表示されます。 

1. [**名前を付けて保存] を** > 選択し、CSV ファイルをローカル コンピューターに保存します。 

1. すべてのアクティビティを検索するとき、または広範な日付範囲で多くの検索結果をダウンロードするには、しばらく時間がかかります。 CSV ファイルのダウンロードが完了すると、ウィンドウの下部にメッセージが表示されます。

## <a name="detailed-properties-in-the-audit-log"></a>監査ログの詳細なプロパティ

次の表では、CSV に含まれるプロパティについて説明します。

|プロパティ|説明|
| - | - |
|activity.category|<p>アクションが実行されたオブジェクトのカテゴリ。 値の例は次のとおりです。</p><p>**ユーザー、割り当て、PartnerInvitation、ロール**</p>|
|activity.objectName|変更されたオブジェクトの名前。|
|activity.operation|実行された操作の種類。 指定できる値は、**作成、更新、削除です**。 |
|activity.resultStatus|<p>アクション ( **activity.operation** プロパティで指定) が成功したかどうかを示します。</p><p>値は **[成功] または [****失敗]** です。</p>|
|activity.tenantId|アクションが実行されたテナントの GUID|
|creationTime|ユーザーがアクティビティを実行したときの ISO 形式の協定世界時 (UTC) の日付と時刻。|
|user.userId|レコードがログに記録されたアクションを実行したユーザー。|
|user.userTenantId|アクションを実行したユーザーのテナントの GUID|


