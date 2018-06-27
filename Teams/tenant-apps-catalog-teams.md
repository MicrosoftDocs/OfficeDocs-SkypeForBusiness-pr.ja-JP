---
title: マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: マイクロソフト チームのテナントのアプリケーション カタログでアプリケーションを発行するためのガイダンスです。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 298caf3cee6fe6af38f22ef9ac7dd85991fd6dba
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "20050458"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a>マイクロソフト チーム テナント アプリケーション カタログにアプリケーションを発行します。
=======================================================

> [!IMPORTANT]
> このページでは、プレリリース版の機能の説明し、リリース前に大幅に変更される可能性が暫定的なコンテンツが含まれています。 任意のスクリーン ショットでは、プレース ホルダーであるし、ものと異なって表示される場合があります。

マイクロソフト チームのテナントのアプリケーション カタログを使用するにはテストし、組織の基幹業務アプリケーションを配布します。 

チーム テナント アプリケーション カタログでは、組織用に構築された基幹業務アプリケーションを配布することができに依存することは、ユーザーに重要なビジネス機能を完了します。 
 
チーム クライアントから直接チーム テナント アプリケーション カタログにアプリケーションを発行できます。

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a>テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。

### <a name="get-a-teams-app-package"></a>チームのアプリケーション パッケージを取得します。

チームのアプリケーション パッケージを作成するには、[チームの App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio)を使用します。 アプリケーション パッケージを作成したらは、エンタープライズ アプリケーションのカタログに追加できます。 テナント内のすべてのユーザーは、アプリケーションのカタログを表示できますが、ときにそれを管理することがある管理者のみです。

### <a name="go-to-the-tenant-apps-catalog"></a>テナント アプリケーション カタログに移動します。

マイクロソフト チーム ストアから、特定の組織 (Contoso など) での新しいセクションを選択します。 ユーザーが組織内では、カタログでアプリケーションを表示でき、チームのメンバーになっているうちにそれらをインストールすることができます。 

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>テナント アプリケーション カタログにアプリケーションを追加します。

ストアから**カスタム アプリケーションのアップロード**を選択して > **の contoso 社のアップロード**します。

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image02.png)

(することもできます**自分または自分のチームのアップロード**をアプリケーションで、またはの選択したチームにのみ使用可能な sideloading と呼ばれる。) 

アプリケーション パッケージに移動し、それを選択します。

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image03.png)

テナント アプリケーション カタログに戻すと、新しいエンタープライズ アプリケーションがあります。 組織のメンバーだけにこのアプリケーションのカタログへのアクセスがあることを忘れないでください。

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>テナント アプリケーション カタログでアプリケーションを更新します。

1. テナント アプリケーション カタログからの選択 [**]** 更新するアプリケーションの右側のトップします。
2. 更新されたアプリケーション パッケージに移動し、それを選択します。

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image04.png)

アプリケーションはバージョン 2.0 に更新されます。 このメニューから会社全体のアプリケーションを削除します。

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Office 365 管理ポータルを使用して、テナントのアプリケーション カタログを管理するには

バグの修正を必要とするアプリケーションがあれば、Office 365 管理ポータル アプリケーションを一時的に無効にできます。 以前の設定は、今すぐセクション社内のアプリケーションに専用です。 どのアプリケーションを有効または無効にすることもできます。

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image05.png)

これは、アプリケーションを完全に削除することがなく、アプリケーションと対話するユーザーをブロックします。 これらのコントロールは柔軟性を管理者に提供し、タイミングを制御、企業内のアプリケーションの管理。 


