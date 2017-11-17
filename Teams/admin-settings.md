---
title: "Microsoft Teams でのアプリの管理設定 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 3e385c1a9a3175d4aaef6ea0eb52d6278c538d94
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams でのアプリの管理設定
==========================================

このセクションでは、単一のサードパーティ サービスによって提供されるタブ、コネクタ、ボット、これらの機能を組み合わせたものをアプリと言います。Office 365 管理ポータルで構成可能な管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。このポリシーでは、許可または禁止するアプリ、新しい外部アプリの動作、アプリのサイドロードを許可するかどうかを指定できます。

**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**

既定では、選択したすべてのアプリに対して [Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)] が有効になります。このポリシーを「**オフ**」にすると、すべての外部サードパーティ アプリが無効化されます。細かく調整して特定の外部アプリを有効にするには、アプリを個別にオフにして無効にすることができます。

**Enable new external apps by default (既定で新しい外部アプリを有効にする)**

Teams アプリ カタログに送られる新しいアプリについて、このスイッチはテナントのユーザーに対して利用可能にするかどうかを制御します。既定では、このポリシーは「**オン**」に設定されています。ユーザーはアプリがチームのアプリ カタログに追加されると同時にそのアプリにアクセスできます。Teams での使用を許可する前にアプリを検証する場合は、このポリシーを「**オフ**」に設定します。「**オフ**」に設定する場合は、新しく追加されるアプリを定期的に評価して、それらのアプリがもたらす最新の革新的機能や追加機能をユーザーが利用できるようにします。

**Allow sideloading of external apps (外部アプリのサイドローディングを許可する)**

権限が与えられたチーム所有者またはメンバーのみが Microsoft Teams でアプリをサイドロードできます。Microsoft Teams でアプリをサイドロードすると、次のような利点があります。

-   Microsoft に送信する前にアプリをテストできる

-   アプリを Office ストアに送信することなく、組織内のユーザーに直接に提供できる.

Microsoft Teams でのアプリのサイドロードについて詳しくは、「[Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631)」(英語版) にアクセスしてください。

![Microsoft Teams の設定の [アプリ] セクションのスクリーンショット](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
