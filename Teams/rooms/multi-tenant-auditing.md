---
title: Microsoft Teams ルーム ポータル
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
ms.openlocfilehash: e5e5cd25385f6e8a71484c57aa9c44da5d4c9cd8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331244"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Teams Rooms Managed サービスの監査ログ

Teams Rooms Managed (TRM) サービスの監査では、ユーザーと管理者がポータルで実行したアクティビティの監査レコードを検索できます。 この機能は既定で有効になっています。 ログをエクスポートして表示するアクセス許可を持つのは、管理対象サービス管理者のみです。

> [!NOTE]
> TRM サービスで実行されたアクションは、監査Microsoft 365ログインOffice 365されません。 

## <a name="exporting-logs"></a>ログのエクスポート

監査ログ検索のすべての結果をエクスポートすると、統合監査ログの生データが、ローカル コンピューターにダウンロードされるコンマ区切り値 (CSV) ファイルにコピーされます。 

**ログをダウンロードするには** 

1. [全般監査 **設定 > ログ] >に移動します**。
1. 関心のあるログの日付範囲を定義するには、[開始日] と [終了日 **]** **を入力します。**

   > [!NOTE]
   > ログは最大 180 日間のみ使用できます。

1. [ログ **のダウンロード] を選択します。**

   ![監査ログの日付範囲](../media/multi-tenant-auditing.png)

   ウィンドウの下部に表示されるメッセージで、CSV ファイルを開く、または保存するように求めるメッセージが表示されます。 

1. [**名前**  >  **を付けて保存]** を選択し、CSV ファイルをローカル コンピューターに保存します。 

1. すべてのアクティビティを検索する場合、または広範な日付範囲で多数の検索結果をダウンロードするには、しばらく時間が必要です。 CSV ファイルのダウンロードが完了すると、ウィンドウの下部にメッセージが表示されます。

## <a name="detailed-properties-in-the-audit-log"></a>監査ログの詳細なプロパティ

次の表では、CSV に含まれるプロパティについて説明します。

|プロパティ|説明|
| - | - |
|activity.category|<p>アクションが実行されたオブジェクトのカテゴリ。 値の例は次のとおりです。</p><p>**ユーザー、割り当て、PartnerInvitation、ロール**</p>|
|activity.objectName|変更されたオブジェクトの名前。|
|activity.operation|実行される操作の種類。 指定できる値は、 **作成、更新、削除です。** |
|activity.resultStatus|<p>アクション **(activity.operation** プロパティで指定) が成功したかどうかを示します。</p><p>値は[成功] **または [** 失敗] **のいずれかです**。</p>|
|activity.tenantId|アクションが実行されたテナントの GUID|
|creationTime|ユーザーがアクティビティを実行した場合の ISO 形式の協定世界時 (UTC) の日付と時刻。|
|user.userId|レコードがログに記録される結果のアクションを実行したユーザー。|
|user.userTenantId|アクションを実行したユーザーのテナントの GUID|


