---
title: Microsoft Teams テナント アプリ カタログにアプリを公開する
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/15/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: マイクロソフト チームのテナントのアプリケーション カタログでアプリケーションを発行するためのガイダンスです。
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebc26292e41328589f302127980f4a303efd46a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226712"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a>Microsoft Teams テナント アプリ カタログにアプリを公開する
=======================================================

マイクロソフト チームのテナントのアプリケーション カタログを使用するにはテストし、組織の基幹業務アプリケーションを配布します。 

チーム テナント アプリケーション カタログでは、組織用に構築された基幹業務アプリケーションを配布することができに依存することは、ユーザーに重要なビジネス機能を完了します。 
 
グローバル管理者の資格情報を使用して、チームのクライアントにサインインし、組織のアプリケーションを発行します。 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a>テナント アプリケーション カタログにチームのクライアントからアプリケーションを発行します。

注: 組織のアプリケーションを発行するのには、グローバル管理者の資格情報を使用してマイクロソフトのチームのクライアントにサインインする必要があります。

### <a name="get-a-teams-app-package"></a>チームのアプリケーション パッケージを取得します。

チームのアプリケーション パッケージを作成するには、[チームの App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)を使用します。 アプリケーション パッケージを作成したらは、エンタープライズ アプリケーションのカタログに追加できます。 テナント内のすべてのユーザーの中に持つことができますビュー現在のみグローバル管理者、アプリケーション カタログを発行し、管理する機能です。 (最終的には、チームを管理できるようになりますも。)

### <a name="go-to-the-tenant-apps-catalog"></a>テナント アプリケーション カタログに移動します。

マイクロソフト チームのクライアントを起動し、グローバル管理者の資格情報を使用してサインインします。 マイクロソフト チーム ストアから、特定の組織 (Contoso など) での新しいセクションを選択します。 ユーザーが組織内では、カタログでアプリケーションを表示でき、チームのメンバーになっているうちにそれらをインストールすることができます。 

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

一時的に Office 365 管理ポータル アプリケーションを無効にすることができます**設定**を選択してバグの修正を必要とするアプリケーションがあれば、 > **サービス & アドイン** > **マイクロソフトのチーム**です。 以前の設定は、今すぐセクション社内のアプリケーションに専用です。 どのアプリケーションを有効または無効にすることもできます。

![スクリーン ショット チームのアプリケーション ストアのアプリ カタログを表示します。](media/private-app-store-teams-image05.png)

これは、アプリケーションを完全に削除することがなく、アプリケーションと対話するユーザーをブロックします。 これらのコントロールは柔軟性を管理者に提供し、タイミングを制御、企業内のアプリケーションの管理。 


