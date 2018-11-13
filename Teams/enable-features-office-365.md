---
title: Office 365 組織でマイクロソフトのチーム機能を管理します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: 有効または無効のタブ、コネクタ、ボット、または 3 つの任意の組み合わせを含む、Office 365 の組織でアプリケーションをマイクロソフトのチームにする方法を説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: f975ed755c66fe644c7097e218dc3be14e7c3165
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295907"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a>Office 365 組織でマイクロソフトのチーム機能を管理します。

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

チームのすべての設定は、新しいマイクロソフトのチームとビジネス管理センターの Skype をすぐに移行されます。 チームがこの機能を Office 365 の管理センターで管理されているとは、アプリケーションです。 

特に明記されていない場合を除き、オプションの規定値はオンです。

> [!NOTE] 
> Teams についての管理設定を管理するには、Office 365 管理センターに移動して、[**設定**] > [**サービスとアドイン**] を開いて、[**Microsoft Teams**] を選択します。 Office 365 管理者としてサインインしている場合は、次のリンクから移動できます。 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

## <a name="office-365-tenant-wide-settings"></a>Office 365 テナント全体の設定 

**テナント全体の設定**] を有効にするまたはアプリケーションを無効にできます。

Teams の**テナント全体の設定**を編集するには、Office 365 管理センターに移動します。 [**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Teams**] の順に選択します。

## <a name="apps"></a>アプリ

アプリとは、サードパーティのサービスによって提供されるタブ、コネクタ、ボットという 3 つの要素のあらゆる組み合わせで構成されているものです。 Office 365 管理センターで構成可能な Teams 管理ポリシーを使用すると、許可する外部サードパーティ アプリを制御することができます。 これらのポリシーでは、読み込み側のアプリケーションを許可するかどうか、どのアプリが許可され、許可されていない外部のアプリケーションの新しい動作を指定できます。 

[**アプリ**] の下で、組織の次の設定を構成できます。 

![[アプリ] セクションのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Microsoft Teams の外部アプリを許可する**: このスイッチがオンになると、ユーザーは Office 365 テナントで利用できるタブやボットを 追加することができます。 
 
    ![[アプリ] セクションの外部アプリの許可コントロールのスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **既定で新しい外部アプリを有効にする**: このスイッチがオンになると、ユーザーは Teams アプリ カタログに新しいアプリが追加されるとそれをすぐにアクティブ化することができます。 新しいアプリに対する制御を行う場合はこのスイッチをオフにします。 これをオフにする場合は、自分の組織で優れた新しいアプリを利用する機会を失うことがないように、新しいアプリについて忘れずに定期的に確認する必要があります。 

- **外部アプリのサイドロードを許可する:** このスイッチがオンになると、ユーザーはカスタムのボットやタブをインストールして有効にすることができます。 

詳細については、[Teams でのアプリの管理設定](admin-settings.md) をご覧ください。 

