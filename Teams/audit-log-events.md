---
title: "Microsoft Teams でイベントの監査ログを検索する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "監査ログから Microsoft Teams データを取得する方法について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 90de6c2267eb2828f2f681287d4b43c001d0ceb4
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Microsoft Teams でイベントの監査ログを検索する
==================================================

監査ログにより、Office 365 サービス全体の重要なイベントをアドホック検索できます。具体的に Microsoft Teams の場合は、次のようなイベントがキャプチャされます。

-   チームの作成

-   チームの削除

-   追加されたチャネル

-   変更された設定

Office 365 全体についての完全なイベント リストは広範囲に及びます。リストは[ここ](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities)で入手することができます。

監査の内容を調査する前に、監査を有効にする必要があります。監査を有効にするには、*セキュリティとコンプライアンス*管理センターに移動します。[*Search for activity (アクティビティの検索)*] で [**Start recording now (すぐにレコーディングを開始)** をクリックします。24 時間後に [*Search & Investigation (検索と調査)*] タブの下にある [*監査ログの検索*] で監査データが利用可能になります。


| |  |
|---------|---------|
|![セキュリティとコンプライアンス センターのホーム ページのスクリーンショット。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>重要     |利用できる監査データは、監査を有効にした時点以降のデータのみです。         |

![セキュリティとコンプライアンス センターの [Audit log search (監査ログの検索)] ページのスクリーンショット。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

監査ログから Microsoft Teams データを取得する方法について説明します。

1.  監査ログ情報を取得するには [セキュリティとコンプライアンス管理センター](https://go.microsoft.com/fwlink/?linkid=855775)に移動します。[*Search & Investigation (検索と調査)*] タブで [**Audit log search (監査ログの検索)**] をクリックします。

    a.  Microsoft Teams では、選択可能な監査アクティビティを次のように定義しています。

![セキュリティとコンプライアンス センターの [Audit log search (監査ログの検索)] ページのスクリーンショット。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  関心のあるアクティビティを選択したら、Microsoft Teams 情報の取得の対象とするデータ範囲とユーザーを指定します。[**検索**] をクリックして、結果を取得します。

3.  この情報は、必要に応じて Excel にエクスポートしたり、フィルタリングできます。


|  | |
|---------|---------|
|![感嘆符アイコン。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br>重要 |これまで監査が有効でなかった場合は、監査を有効にしないと、データが監査ログに表示されません。         |
