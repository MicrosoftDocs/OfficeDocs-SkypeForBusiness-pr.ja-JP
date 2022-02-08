---
title: 許可されたメンバーの選択
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 常設チャット ルームの作成と管理は、カテゴリの正しい使用によりはるかに簡単です。 常設チャット管理者は、カテゴリごとに AllowedMembers と Creators を定義できます。また、カテゴリ内に作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、コントロール パネルまたは管理者のコマンドレットを使用してWindows PowerShell管理します。
ms.openlocfilehash: 69e75459e7b94981a2a32885e6db0ea5ebea9804
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386015"
---
# <a name="select-allowed-members"></a>許可されたメンバーの選択

常設チャット ルームの作成と管理は、カテゴリの正しい使用によりはるかに簡単です。 常設チャット管理者は、 **カテゴリごとに AllowedMembers** と **Creators** を定義できます。また、カテゴリ内に作成されたチャット ルームに適用される既定のチャット ルームの設定と動作を定義することもできます。 常設チャット管理者は、コントロール パネルまたは管理者のコマンドレットを使用してWindows PowerShell管理します。

カテゴリの作成者として識別されるユーザー、組織単位 (OUs)、およびユーザー グループは、カテゴリ内に会議室を作成できる唯一の個人およびグループです。 カテゴリを作成したら、カテゴリの **AllowedMembers** リストからユーザー、OUs、およびユーザー グループをチャット ルームの管理者として選択し、メンバーがルームを管理および参加できます。

## <a name="tasks-that-you-can-perform"></a>実行できるタスク

[許可されたメンバーの選択] ページで次 **のタスクを実行** できます。

- [カテゴリの構成](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [常設チャット サーバーの新機能](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

コントロール パネルを使用して実行できるさまざまな手順の詳細については、「Skype for Business Server [2015](../../manage/manage.md)」を参照Skype for Business Serverしてください。

## <a name="to-configure-categories-for-chat-rooms"></a>チャット ルームのカテゴリを構成するには

[**メンバーシップ**] の [許可されたメンバー] セクションで、カテゴリに属するチャット ルームのメンバーとして追加できるユーザーおよび他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。 カテゴリで許可されているプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示の場合を指定しない限り、ディレクトリ内で検索できるのは会議室のメンバーのみです)。


常設チャット サーバーの機能の詳細については、「計画」のドキュメントの「 [常設](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) チャット サーバーの概要」を参照してください。 常設チャット サーバー構成の操作の詳細については、「展開」[](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)のドキュメントの「常設チャット サーバーの構成」および「操作」のドキュメントの「[Lync Server 2013](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) の管理」を参照してください。

## <a name="see-also"></a>関連項目

[Persistent Chat のメンバーシップについて](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)