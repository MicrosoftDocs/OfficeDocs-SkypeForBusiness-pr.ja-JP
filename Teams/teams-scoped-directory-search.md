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
description: Microsoft Teams の範囲指定ディレクトリ検索を使用して、ディレクトリのカスタマイズされたビューを提供する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ede4b60878dbdd44edf369b0a3c1bb861ffe366
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094027"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Microsoft Teams の範囲指定ディレクトリ検索を使用する

Microsoft Teams の範囲指定ディレクトリ検索を使用すると、組織は、ユーザーが組織内の他のユーザーを見つけて通信する方法を制御する仮想境界を作成できます。 

Microsoft Teams を使用すると、組織はディレクトリのカスタム ビューをユーザーに提供できます。 Microsoft Teams では [、Information Barrier ポリシーを使用して](/microsoft-365/compliance/information-barriers) 、これらのカスタム ビューをサポートします。 ポリシーを有効にすると、他のユーザーの検索によって返される結果 (チャットの開始やチームへのメンバーの追加など) は、構成されたポリシーに従って範囲指定されます。 対象範囲検索が有効な場合、ユーザーはチームを検索または検出できますが、アクティブな Information Barrier ポリシーの許可に従って、これらのチームの既存のメンバーはユーザーを追加できます。

> [!NOTE]
> Exchange ハイブリッド環境では、この機能は Exchange Online メールボックスでのみ動作し、オンプレミスのメールボックスでは動作しません。

## <a name="when-should-you-use-scoped-directory-searches"></a>範囲指定されたディレクトリ検索を使用する必要がありますか?

範囲指定されたディレクトリ検索のメリットを受けるシナリオは、アドレス帳ポリシーのシナリオと似ています。 たとえば、次のような状況で、範囲指定されたディレクトリ検索を使用できます。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。 
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。 
 
アドレス帳ポリシーの使い方については、Exchange Online の [Information Barrier ポリシーを参照してください](/microsoft-365/compliance/information-barriers)。

> [!IMPORTANT]
> アドレス帳ポリシーは、ディレクトリの観点からユーザーを仮想的に分離するだけのポリシーです。 また、新しいアドレス帳ポリシーまたは更新されたアドレス帳ポリシーが適用される前に、既にキャッシュされているユーザー データは、最大 30 日間ユーザーが利用できます。

## <a name="turn-on-scoped-directory-search"></a>範囲指定されたディレクトリ検索を有効にする

1. Information Barrier ポリシーを使用して、組織を仮想サブグループに構成します。 詳細については、「情報バリア [ポリシーの定義」を参照してください](/microsoft-365/compliance/information-barriers-policies)。

2. Microsoft Teams 管理センターで、組織全体の **設定 Teams の設定**  >  **を選択します**。

3. [ **検索] の**[Exchange アドレス帳ポリシー **(ABP)** を使用する Teams のスコープ ディレクトリ検索] の横で、[オン] をオン **にします**。

    ![Microsoft Teams 管理センターでの範囲指定ディレクトリ検索](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> この変更は、複製に数時間かかる場合があります。