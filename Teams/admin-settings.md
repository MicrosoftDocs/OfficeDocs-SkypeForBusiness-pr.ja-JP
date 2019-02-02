---
title: Microsoft Teams でのアプリの管理設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: 外部アプリのサイドロードなど、Microsoft Teams でのアプリの許可と有効化について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: da73768f69159c32543d0843139facc2b9ef4f9a
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706356"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams でのアプリの管理設定
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

アプリケーションは、タブ、コネクタ、ボット、またはチーム (ファースト パーティのアプリケーションとも呼ばれる既定アプリケーション) または (外部のアプリケーションとも呼ばれます)、サード パーティによって提供されるこれら 3 つの任意の組み合わせです。 Microsoft 365 管理センターを有効にして既定のアプリケーションを無効にして外部のアプリケーションを制御する設定を構成します。 これらの設定を使用して、読み込み側のアプリケーションを許可するかどうか、外部コンテンツが許可され、許可されていない外部のアプリケーションの新しい動作を指定できます。

 チームでのアプリケーションの管理設定を管理する Microsoft 365 の管理ページに移動し、**設定**を選択して > **サービス & アドイン** > **マイクロソフトのチーム**です。 Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

アプリの管理設定の詳細については、次のビデオをご覧ください。 
 
|  |  |
|---------|---------|
| Managing the App Experience in Microsoft Teams (Microsoft Teams でのアプリの機能と操作性を管理する)   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Allow external apps in Teams (Teams で外部アプリを許可する)

既定では、[**Allow external apps in Microsoft Teams (Microsoft Teams で外部アプリを許可する)**] がオンになり、すべてのアプリが選択されます。  この設定をオフにすると、外部のサードパーティのアプリケーションをすべて無効となります。 

## <a name="enable-new-external-apps-by-default"></a>Enable new external apps by default (既定で新しい外部アプリを有効にする)

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:トロフィー: ベスト プラクティス: 外部アプリを個別に管理する 
 
一部のアプリをオンにする (その他のアプリはオフにする) には、[**Allow sideloading of external apps (外部アプリのサイドロードを許可する)**] をオフにします。 自分のユーザーに使用されないようにするアプリをすべてオフにします。 オプション: [**Enable new external apps by default (既定で新しい外部アプリを有効にする)**] をオフにします (新しいアプリを制御する場合)。 

> [!NOTE]
> 、マイクロソフトによって作成されたものなど、既定のアプリケーションは、**既定では、新しい外部アプリケーションを有効にする**設定の影響を受けません。 マイクロソフトからリリースされたときに既定では、新しいアプリケーションが有効になります。

この設定をオンにすると、新しいアプリのユーザーがアクティブにチーム アプリケーション カタログに追加するいるとすぐに。 Teams アプリ カタログを開くには、Teams の下部にある [**ストア**] をクリックして、[**アプリ**] をクリックします。 どのアプリが利用できるかを制御する場合は、この設定をオフにします。 これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。 

サイドローディングは、チームに直接 zip ファイルをアップロードすることによって Teams にアプリを追加する方法です。 サイドローディングにより、開発途中のアプリをテストすることができます。 内部使用に限定するアプリを構築して、Office ストアの Teams アプリ カタログに送らずにチーム内で共有することができます。 

チーム所有者またはアクセス許可が付与されたメンバーのみが、アプリを Teams にサイドロードすることができます。  

![拡張の外部アプリケーションでの画面です]。(media/teams-tenant-wide-settings-external-apps.png "外部のアプリケーションを示す展開された外部のアプリケーション セクションのスクリーン ショット")

## <a name="creating-and-uploading-app-packages"></a>アプリのパッケージの作成とアップロード 

アプリケーションに関する詳細については、[チーム開発のアプリケーション](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview)を参照してください。 



