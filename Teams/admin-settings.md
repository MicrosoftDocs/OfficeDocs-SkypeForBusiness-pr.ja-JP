---
title: "Microsoft Teams でのアプリの管理設定"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。"
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: ee1c79b6d6d73e5fc702fe55b9e5aee8a7aae793
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams でのアプリの管理設定
==========================================

アプリとは、単一のサードパーティ サービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。Office 365 管理センターで構成可能な管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。このポリシーでは、許可または禁止するアプリ、新しい外部アプリの動作、アプリのサイドロードを許可するかどうかを指定できます。

> [!NOTE]
> Teams のアプリについての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。 Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

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
