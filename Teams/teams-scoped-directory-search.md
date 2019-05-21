---
title: Microsoft Teams の範囲指定ディレクトリ検索を使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Microsoft Teams のスコープ指定ディレクトリ検索を使用して、ディレクトリのカスタマイズされたビューを提供する方法について説明します。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3b51b56b8cc8a1f08d756cdab245915a2ac6824
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226654"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft Teams の範囲指定ディレクトリ検索を使用する

Microsoft Teams 範囲指定ディレクトリ検索を使用すると、組織は、ユーザーが組織内の他のユーザーを検索して通信する方法を制御する仮想境界を作成することができます。 

Microsoft Teams を使用すると、組織はディレクトリのカスタムビューをユーザーに提供できます。 Microsoft Teams では、これらのカスタムビューをサポートするために[Exchange アドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)が使用されています。 ポリシーを有効にすると、他のユーザーの検索結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲設定されます。 スコープ指定された検索が有効になっている場合、ユーザーはチームを検索または検出できません。 

## <a name="when-should-you-use-scoped-directory-searches"></a>スコープディレクトリ検索を使用する場合

スコープを指定したディレクトリ検索を利用するシナリオは、アドレス帳ポリシーのシナリオと似ています。 たとえば、次のような場合には、スコープ指定されたディレクトリ検索を使用することができます。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。 
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。 
 
アドレス帳ポリシーの使用方法については、「 [Exchange Online のアドレス帳ポリシー](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)」を参照してください。

> [!IMPORTANT]
> アドレス帳ポリシーは、ディレクトリの観点からのユーザーの仮想的な分離のみを提供します。 ユーザーは、完全なメールアドレスを提供して、他のユーザーとの通信を開始することができます。 また、新規または更新されたアドレス帳ポリシーを適用する前に、既にキャッシュされていたすべてのユーザーデータは、最大30日間はユーザーに対して利用可能になることに注意する必要があります。

## <a name="enable-scoped-directory-search"></a>スコープ指定されたディレクトリ検索を有効にする

1.  アドレス帳ポリシーを使用して、組織を仮想サブグループに構成します。 詳細については、「[アドレス帳ポリシーの手順](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)」を参照してください。

2.  Microsoft 365 管理センターにサインインし、[**管理センター**]、[ **Teams & Skype**] の順に選択します。
 
3.  Microsoft Teams 管理センターで、[**組織全体の設定** > **チームの設定**] を選択します。

4.  [**検索**] の [ **Exchange アドレス帳ポリシー (apb) を使用して Teams で検索**する] の横**** にある [オン] に切り替えます。 

    ![Microsoft Teams 管理センターでのスコープディレクトリ検索](media/teams-scoped-directory-search-image1.png)

> [!NOTE]
> ハイブリッド構成 (Exchange オンプレミスの Teams) では、範囲指定検索モードはサポートされません。 

