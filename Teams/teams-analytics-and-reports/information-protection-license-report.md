---
title: Microsoft Teams情報保護ライセンス レポート
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターの Teams Information Protection ライセンス レポートを使用して、組織内のアプリが変更通知イベント サブスクリプション API を使用している方法を確認する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44ab006bdbc08ea3b93f46faf9df0f62955814e3
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732656"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams情報保護ライセンス レポート

Teams 情報保護ライセンス レポートは、テナント レベル (/teams/getAllMessage または /chats/getAllMessages) で作成、更新、または削除されたメッセージをリッスンする通知イベントの変更をサブスクライブしているアプリに関する分析情報を提供します。 [](/graph/api/resources/subscription?view=graph-rest-1.0) [](/graph/api/resources/webhooks?view=graph-rest-1.0) メッセージに対応する変更通知は、ユーザーが必要なライセンス を持つ場合にのみ正常 [に送信されます](/graph/teams-licenses)。  特定のユーザーによってトリガーされた変更通知の数を確認できます。


## <a name="view-the-information-protection-license-report"></a>情報保護ライセンス レポートを表示する

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. 管理センターの左側のナビゲーションで、[分析Microsoft Teamsレポート] &**レポート]**  >  **を選択します**。 [レポートの **表示] タブの** [レポート] **で、[Information** **Protection License] を選択します**。
2. [ **日付範囲] で** 範囲を選択します。
3. [アプリ **] で** アプリを選択し、[レポートの実行] **を選択します**。

    ![吹き出しTeams付き、Teams情報保護ライセンス レポートのスクリーンショット。](../media/teams-info-protection-license-report-with-callouts.png "吹き出しTeams付き、Teams情報保護ライセンス レポートのスクリーンショット")

## <a name="interpret-the-report"></a>レポートを解釈する

|Callout |説明  |
|--------|-------------|
|**1**   |情報保護ライセンス レポートでは、過去 7 日間、30 日間、または 90 日間の傾向を確認できます。 |
|**2**   |アプリ名には、日付範囲で選択された過去 n 日間のメッセージの通知イベントを変更するためにサブスクライブしているすべてのアプリの一覧が表示されます。 |
|**3**   |テーブルには、選択したアプリのユーザーごとの使用状況の内訳が表示されます。<ul><li>**表示名** はユーザーの表示名です。 表示名を選択して、管理センターのユーザーの詳細ページMicrosoft Teamsします。</li><li>**Has Required License** is yes if the user has one required licenses as defined (here)[ https://docs.microsoft.com/en-us/graph/teams-licenses ]. ユーザーが必要なライセンスを持ってない場合は、[ライセンスの割り当て] リンクが表示されます。このリンクは、Microsoft 管理センターのユーザーのライセンスの詳細ページに移動します **([** ユーザーのアクティブ ユーザー] >選択します  >  )。</li><li>**ライセンスで保護されたイベント** は、そのユーザーによって作成、更新、または削除されたメッセージに対してアプリに送信される一意の変更通知イベントの数です。</li></ul> |
|**4**   |レポートを CSV ファイルにエクスポートしてオフライン分析します。 [**エクスポート] をExcel** し、[ダウンロード]**タブを選択** します。[**ダウンロード]** を選択して、準備ができたらレポートをダウンロードします。 |
|**5**   |レポートを CSV ファイルにエクスポートしてオフライン分析します。 [**エクスポート] をExcel** し、[ダウンロード]**タブを選択** します。[**ダウンロード]** を選択して、準備ができたらレポートをダウンロードします。 レポートを Excel で表示すると、ユーザーのユーザー ID とメールアドレスを表す [ID] 列と [電子メール] 列も表示されます。 |

## <a name="make-the-user-specific-data-anonymous"></a>ユーザー固有のデータを匿名にする

ユーザー アクティビティ レポートTeamsデータを匿名にする場合は、グローバル管理者である必要があります。 これにより、レポートとそのエクスポートの表示名、電子メール、Azure AD ID などの識別可能な情報が非表示になります。

1. [組織Microsoft 365 管理センター] に移動設定、[設定] タブの [レポート \> ] を **選択します**。
    
2. [ **レポート]** を選択し、[匿名識別子 **を表示する] を選択します**。 この設定は、管理センターと管理センターのMicrosoft 365 管理センターレポートTeams適用されます。
  
3. [変更の **保存] を選択します**。
