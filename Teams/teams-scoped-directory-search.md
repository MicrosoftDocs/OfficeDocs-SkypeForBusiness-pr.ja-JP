---
title: Teamsでディレクトリを検索するときにユーザーが表示できるユーザーを制限する
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Teamsでディレクトリを検索するときに表示できるユーザーを制限する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046429"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>Teamsでディレクトリを検索するときにユーザーが表示できるユーザーを制限する

Microsoft Teamsでは、組織はディレクトリのカスタム ビューをユーザーに提供できます。 これらのビューは、次の場合に役立ちます。

- 所属する組織において、テナント内に複数の会社があり、それらを切り離された状態で維持する場合。
- ビジネス ポリシーでは、組織内の特定のグループが相互に通信できないようにする必要があります。
- 所属する学校において、教職員と学生との間のチャットを制限する必要がある場合。

Teamsでディレクトリを検索するときにユーザーが表示できるユーザーを制限するには、次の 2 つのオプションがあります。

- [Microsoft Teamsの情報バリア](/MicrosoftTeams/information-barriers-in-teams)
- [Exchange Onlineのアドレス帳ポリシー](/exchange/address-books/address-book-policies/address-book-policies)

どちらのオプションを使用する場合も、Teams管理センターで名前による検索を有効にする必要があります。

組織が [必要なライセンスとアクセス許可](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions)を満たしている場合は、情報バリアを使用することをお勧めします。

名前で検索を有効にするには

1. Microsoft Teams管理センターで、**Teams** >  **Teams設定** を選択します。

1. [**名前による検索**] で、[**Exchange アドレス帳ポリシーを使用したスコープ ディレクトリ検索**] の横にあるトグル **[オン]** をオンにします。

> [!Note]
> この変更が有効になるには数時間かかる場合があります。
> 
> 名前で検索を有効にすると、[チームの **検索**] ボックスと [参加] の一覧の公開チームが非表示になるか、Teamsで **チームを作成します**。 また、Teamsの上部にあるコマンド ボックスに入力`/join`して、チームへの参加も無効になります。
