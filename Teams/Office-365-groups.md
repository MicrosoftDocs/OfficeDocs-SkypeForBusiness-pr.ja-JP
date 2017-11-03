---
title: "Office 365 グループと Microsoft Teams | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Office 365 グループとグループ メンバーシップがどのように Microsoft Teams と連携しているかについて説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 45a3607778d87e1de075468101a9f7e1a081688e
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2017
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 グループと Microsoft Teams
=====================================

Office 365 グループは Office 365 のクロスアプリケーションのメンバーシップ サービスです。基本的なレベルでは、Office 365 グループはメンバーのリストを含む Azure Active Directory のオブジェクトです。さらに、このオブジェクトには SharePoint チーム サイト、Yammer グループ、Exchange メールボックスのリソース、Planner、PowerBI、OneNote などの関連ワークロードとの疎結合も含まれています。Active Directory のその他のグループベースのセキュリティ オブジェクトと同様にグループにユーザーを追加したり、グループからユーザーを削除することができます。

Office 365 の管理者は Office 365 グループの定義やメンバーの追加を行うことができ、Exchange 共有メールボックス、SharePoint ドキュメント ライブラリなどの機能も利用することができます。グループについて詳しくは、「[Office 365 グループの概要](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)」をご覧ください。

<a name="how-office-365-groups-work"></a>Office 365 グループについて
--------------------------

Microsoft Teams のチームを作成することは、最終的には SharePoint ドキュメント ライブラリ、OneNote ノートブック、その他の Office 365 クラウド アプリケーションと関連付けられた Office 365 グループを作成することを意味します。チームを作成しているユーザーが既存の Office 365 パブリックまたはプライベート グループの所有者である場合は、Teams の機能をグループに追加できます。追加を行うと、チャット メッセージ、ドキュメント、OneNote、その他のオブジェクトが配置される既定の「全般」チャネルが作成されます。そのチャネルのドキュメント ライブラリを表示すると、チームのチャネルを表す「全般」フォルダーが表示されます。さらに重要な点は、ドキュメント ライブラリ内で独自のフォルダー構造を作成しても、それはチャネルとして Teams に**伝播されません**。現時点では、Teams から SharePoint にのみ伝播されます。

|||
|---------|---------|
|  ![注意アイコン。](media/Understand_Office_365_groups_and_Microsoft_Teams_image1.png) 注意    |Office 365 グループを削除すると、永続的な Outlook/OWA の会話や Teams 会議への招待状のメールボックス エイリアスが削除され、SharePoint サイトに削除のマークが付けられます。チームを削除した時点からそれが Outlook に反映されるまでに約 20 分かかります。Teams クライアントからチームを削除すると、そのチームのすべてのメンバーの表示からそのチームが即座に削除されます。Teams の機能を有効にしている Office 365 グループからメンバーを削除すると、削除したメンバーの Teams クライアントの表示からそのチームが削除されるまでに約 1 時間の遅延が発生します。         |


<a name="group-membership"></a>グループ メンバーシップ
----------------

ユーザーが利用できる機能は、グループ メンバーシップを入手した場所によって異なります。たとえば、チームのメンバーを削除すると、そのメンバーは Office 365 グループからも削除されます。グループから削除すると、即座にチームが削除され、Teams クライアントからチャネルが削除されます。Office 365 管理ポータルを使用してグループからメンバーを削除すると、そのメンバーは SharePoint Online ドキュメント ライブラリ、Yammer グループ、共有 OneNote といったその他のコラボレーション機能へのアクセスを失います。ただし、削除後もチームのチャット機能には約 1 時間アクセスできます。

Teams の「メンバー管理」を行う場合、Teams クライアントを介して追加/削除機能を使用することで、適切なカスケード アクセス コントロールをその他の依存するクラウド アプリケーションに適用できます。さらに、ユーザーに整然としていない使用感が生じて、以前アクセスできていたリソースに、(特定のサービス コンポーネントへのアクセスが追加または取り消される次回の同期サイクルまで) 引き続きアクセスできるという印象を残さないようにします。
