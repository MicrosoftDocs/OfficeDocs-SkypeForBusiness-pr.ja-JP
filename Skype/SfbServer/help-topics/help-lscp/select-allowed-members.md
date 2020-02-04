---
title: 許可されたメンバーの選択
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 永続的なチャットルームの作成と管理は、カテゴリを適切に使用することで非常に簡単になります。 常設チャット管理者は、各カテゴリの AllowedMembers とクリエーターを定義できます。また、カテゴリで作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作も定義できます。 常設チャット管理者は、コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリの作成と管理を行います。
ms.openlocfilehash: 916077fe25e1616888dd58dc40f0ef0f14c61e7a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699702"
---
# <a name="select-allowed-members"></a>許可されたメンバーの選択

永続的なチャットルームの作成と管理は、カテゴリを適切に使用することで非常に簡単になります。 常設チャット管理者は、各カテゴリの**Allowedmembers**と**クリエーター**を定義できます。また、カテゴリで作成されたすべてのチャットルームに適用される既定のチャットルームの設定と動作も定義できます。 常設チャット管理者は、コントロールパネルまたは Windows PowerShell コマンドレットを使用して、カテゴリの作成と管理を行います。

カテゴリの Creators として特定されるユーザー、組織単位 (OU)、ユーザー グループは、そのカテゴリのチャット ルームの作成を許可されている個人およびグループです。 カテゴリを作成した後、カテゴリの**allowedmembers**リストからユーザー、ou、ユーザーグループを選ぶことができます。チャットルーム管理者として、会議室への参加を管理するメンバーとして選択できます。

## <a name="tasks-that-you-can-perform"></a>実行できるタスク

[**許可されたメンバーの選択**] ページでは、次のタスクを実行できます。

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Skype for Business Server コントロールパネルを使用して実行できるさまざまな手順の詳細については、「Skype for business [server 2015 を管理](../../manage/manage.md)する」を参照してください。

## <a name="to-configure-categories-for-chat-rooms"></a>チャット ルームのカテゴリを構成するには

[許可された**メンバー** ] セクションの [**メンバーシップ**] で、カテゴリに属するチャットルームのメンバーとして追加することを許可されているユーザーおよびその他の Active Directory ドメインサービスプリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。 カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索することができます (ルームが非表示になっている場合を除き、ルームのメンバーだけがディレクトリ内で検索できます)。


常設チャットサーバーの機能と機能の詳細については、計画ドキュメントの「[常設チャットサーバーの概要](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)」を参照してください。 常設チャットサーバーの構成の使用について詳しくは、「展開ドキュメントで[常設チャットサーバーを構成](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)する」と「運用ドキュメントで[Lync Server 2013、常設チャットサーバーを管理](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)する」をご覧ください。

## <a name="see-also"></a>関連項目

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
