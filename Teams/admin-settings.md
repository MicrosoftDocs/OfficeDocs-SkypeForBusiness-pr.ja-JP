---
title: Microsoft Teams でのアプリの管理設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: 外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50490b08986f1a8f312aa79d5492b1ed8a97ecc8
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams でのアプリの管理設定
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

アプリケーションは、タブ、コネクタ、ボット、またはサードパーティ製のサービスによって提供されるこれら 3 つの任意の組み合わせです。制御をする外部のサードパーティのアプリケーションを許可する Office 365 の管理ページで構成可能なチーム管理ポリシーがあります。これらのポリシーでは、読み込み側のアプリケーションを許可するかどうか、どのアプリが許可され、許可されていない外部のアプリケーションの新しい動作を指定できます。

> [!NOTE]
> Teams のアプリについての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。 Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

アプリの管理設定の詳細については、次のビデオをご覧ください。 
 
|  |  |
|---------|---------|
| Managing the App Experience in Microsoft Teams (Microsoft Teams でのアプリの機能と操作性を管理する)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Allow external apps in Teams (Teams で外部アプリを許可する)

既定では、[**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**] がオンになり、すべてのアプリが選択されます。  このスイッチをオフにすると、すべての外部サード パーティ アプリが無効になります。 

## <a name="enable-new-external-apps-by-default"></a>Enable new external apps by default (既定で新しい外部アプリを有効にする)

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:トロフィー: ベスト プラクティス: 外部アプリを個別に管理する 
 
一部のアプリをオンにする (その他のアプリはオフにする) には、[**Allow sideloading of external apps (外部アプリのサイドロードを許可する)**] をオフにします。 自分のユーザーに使用されないようにするアプリをすべてオフにします。 オプション: [**Enable new external apps by default (既定で新しい外部アプリを有効にする)**] をオフにします (新しいアプリを制御する場合)。 

> [!NOTE]
> 、マイクロソフトによって作成されたものなど、既定のアプリケーションは、**既定では、新しい外部アプリケーションを有効にする**設定の影響を受けません。

このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。 Teams アプリ カタログを開くには、Teams の下部にある [**ストア**] をクリックして、[**アプリ**] をクリックします。 どのアプリを利用できるようにするかを制御する場合は、このスイッチをオフにします。 これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。 

サイドローディングは、チームに直接 zip ファイルをアップロードすることによって Teams にアプリを追加する方法です。 サイドローディングにより、開発途中のアプリをテストすることができます。 内部使用に限定するアプリを構築して、Office ストアの Teams アプリ カタログに送らずにチーム内で共有することができます。 

チーム所有者またはアクセス許可が付与されたメンバーのみが、アプリを Teams にサイドロードすることができます。  

![テナント全体の設定の展開されたアプリケーションのスクリーン ショットです。](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a>アプリのパッケージの作成とアップロード 

アプリケーションに関する詳細については、[チーム開発のアプリケーション](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)を参照してください。 



