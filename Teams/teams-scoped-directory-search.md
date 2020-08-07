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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams のスコープ指定ディレクトリ検索を使用して、ディレクトリのカスタマイズされたビューを提供する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4152a2ac9ee50372dbc0fdb423d0d85c3026433
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584076"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft Teams の範囲指定ディレクトリ検索を使用する

Microsoft Teams 範囲指定ディレクトリ検索を使用すると、組織は、ユーザーが組織内の他のユーザーを検索して通信する方法を制御する仮想境界を作成することができます。 

Microsoft Teams を使用すると、組織はディレクトリのカスタムビューをユーザーに提供できます。 Microsoft Teams では、これらのカスタムビューをサポートするために、[情報バリアポリシー](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)を使用しています。 ポリシーを有効にすると、他のユーザーの検索結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲設定されます。 スコープ指定された検索が有効になっている場合、ユーザーはチームを検索または検出できません。 

> [!NOTE]
> Exchange ハイブリッド環境では、この機能は Exchange Online のメールボックスでのみ機能し、オンプレミスのメールボックスには使用できません。

## <a name="when-should-you-use-scoped-directory-searches"></a>スコープディレクトリ検索を使用する場合

スコープを指定したディレクトリ検索を利用するシナリオは、アドレス帳ポリシーのシナリオと似ています。 たとえば、次のような場合には、スコープ指定されたディレクトリ検索を使用することができます。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。 
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。 
 
アドレス帳ポリシーの使用方法については、「 [Exchange Online で情報バリアポリシー](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)」を参照してください。

> [!IMPORTANT]
> アドレス帳ポリシーは、ディレクトリの観点からのユーザーの仮想的な分離のみを提供します。 ユーザーは、完全なメールアドレスを提供して、他のユーザーとの通信を開始することができます。 また、新規または更新されたアドレス帳ポリシーを適用する前に、既にキャッシュされていたすべてのユーザーデータは、最大30日間はユーザーに対して利用可能になることに注意する必要があります。

## <a name="turn-on-scoped-directory-search"></a>スコープディレクトリ検索を有効にする

1. 情報バリアポリシーを使用して、組織を仮想サブグループに構成します。 詳細については、「[情報バリアポリシーを定義](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)する」を参照してください。

2. Microsoft Teams 管理センターで、[**組織全体の設定**チームの設定] を選択し  >  **Teams settings**ます。

3. [**検索**] の [ **Exchange アドレス帳ポリシー (abp) を使用して Teams で検索**する] の横にある [オン **] に切り替えます。**

    ![Microsoft Teams 管理センターでのスコープディレクトリ検索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> この変更は、複製に数時間かかる場合があります。
