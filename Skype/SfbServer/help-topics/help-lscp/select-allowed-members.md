---
title: 許可されたメンバーの選択
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: カテゴリを正しく使用すると、常設チャット ルームの作成と管理がはるかに簡単になります。 常設チャット管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、コントロール パネルまたは管理コマンドレットを使用して、カテゴリをWindows PowerShellします。
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829137"
---
# <a name="select-allowed-members"></a>許可されたメンバーの選択

カテゴリを正しく使用すると、常設チャット ルームの作成と管理がはるかに簡単になります。 常設チャット管理者は、カテゴリごとに **AllowedMembers** と **Creators** を定義できます。また、カテゴリで作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、コントロール パネルまたはカスタム コマンドレットを使用して、カテゴリをWindows PowerShellします。

カテゴリの作成者として識別されるユーザー、組織単位 (US)、およびユーザー グループは、カテゴリにルームを作成できる唯一の個人およびグループです。 カテゴリが作成されると、カテゴリの **AllowedMembers** リストからユーザー、US、およびユーザー グループをチャット ルームのマネージャーおよびメンバーとして選択し、ルームを管理および参加できます。

## <a name="tasks-that-you-can-perform"></a>実行できるタスク

[許可されたメンバーの選択] ページでは、 **次のタスクを実行** できます。

- [カテゴリを構成する](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [常設チャット サーバーの新機能](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Skype for Business Server 2015](../../manage/manage.md)の管理」を参照してください。

## <a name="to-configure-categories-for-chat-rooms"></a>チャット ルームのカテゴリを構成するには

[**メンバーシップ**] の[許可されるメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。 カテゴリによって許可されるプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ルームのメンバーだけがディレクトリで検索できます)。


常設チャット サーバーの機能の詳細については、「計画」のドキュメントの [「Overview of Persistent Chat Server」](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) を参照してください。 常設チャット サーバーの構成の操作の詳細については、「展開」のドキュメントの [「Configuring Persistent Chat Server」](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) および「操作」のドキュメントの [「Managing Lync Server 2013, Persistent Chat Server」](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) を参照してください。

## <a name="see-also"></a>関連項目

[Persistent Chat のメンバーシップについて](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
