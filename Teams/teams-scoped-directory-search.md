---
title: Microsoft Teams の範囲指定ディレクトリ検索を使用する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: スコープを指定したディレクトリMicrosoft Teamsを使用して、ディレクトリのカスタマイズされたビューを提供する方法について学習します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82fb18f60bf812bcc6b7535cdbf2589e60e1d399
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627429"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft Teams の範囲指定ディレクトリ検索を使用する

Microsoft Teamsを使用すると、組織は、ユーザーが組織内の他のユーザーを見つけて通信する方法を制御する仮想境界を作成できます。 

Microsoft Teams、組織はディレクトリのカスタム ビューをユーザーに提供できます。 Microsoft Teams、Information [Barrier ポリシーを使用して、](/microsoft-365/compliance/information-barriers)これらのカスタム ビューをサポートします。 ポリシーが有効になると、他のユーザーの検索によって返される結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲が設定されます。 スコープ検索が有効な場合、ユーザーはチームを検索または検出できますが、アクティブな Information Barrier ポリシーで許可されている通り、それらのチームの既存のメンバーはユーザーを追加できます。

> [!NOTE]
> ハイブリッドExchangeでは、この機能はオンプレミスのメールボックスではなく、Exchange Online メールボックスでのみ機能します。

「アドレス帳[ポリシー」も参照Exchange Online。](/exchange/address-books/address-book-policies/address-book-policies)

## <a name="when-should-you-use-scoped-directory-searches"></a>スコープ指定されたディレクトリ検索を使用する必要が生じ

範囲指定されたディレクトリ検索のメリットを得るシナリオは、アドレス帳ポリシーのシナリオと似ています。 たとえば、次のような状況で、範囲指定されたディレクトリ検索を使用できます。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。 
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。 
 
アドレス帳ポリシーを使用する方法については、次の記事の「Information Barrier policies (情報バリア ポリシー [)」をExchange Online。](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> アドレス帳ポリシーは、ディレクトリの観点からのユーザーの仮想的な分離のみを提供します。 また、新しいアドレス帳ポリシーまたは更新されたアドレス帳ポリシーを適用する前に、既にキャッシュされているユーザー データは、最大 30 日間ユーザーが使用できる状態が維持されます。

## <a name="turn-on-scoped-directory-search"></a>スコープを指定したディレクトリ検索を有効にする

1. Information Barrier ポリシーを使用して、組織を仮想サブグループに構成します。 詳細については、「情報バリア ポリシー [の定義」を参照してください](/microsoft-365/compliance/information-barriers-policies)。

2. 管理センター Microsoft Teams、[組織全体の設定] を選択し **、[** 設定  >  **] Teamsします**。

3. [**検索]** で、[アドレス帳ポリシー **(ABP)** Teamsを使用Exchangeのスコープ ディレクトリ検索] の横にある [オン] を **オンにします**。

    ![管理センターでのスコープMicrosoft Teams検索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> この変更は、レプリケートに数時間かかる場合があります。
