---
title: ユーザーのグループ通話ピックアップを有効にし、Skype for Business でグループ番号を割り当てる
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Skype for Business Server のグループ通話ピックアップでユーザーを有効エンタープライズ VoIPグループ番号を割り当てる。
ms.openlocfilehash: 5469e9634e16b855993518092114184a2dca7359
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111833"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>ユーザーのグループ通話ピックアップを有効にし、Skype for Business でグループ番号を割り当てる

Skype for Business Server のグループ通話ピックアップでユーザーを有効エンタープライズ VoIPグループ番号を割り当てる。

コール パーク オービット テーブルに通話ピックアップ グループ番号を追加した後、SEFAUtil ツールを使用してグループ番号をユーザーに割り当て、グループ通話ピックアップを有効にします。

> [!NOTE]
> ハイブリッド展開では、グループ通話ピックアップ グループをオンラインのユーザーに割り当てない。 オンラインに参加しているユーザーは、グループ通話ピックアップに参加できません。 つまり、他のユーザーが通話に応答することはできません。また、他のユーザーへの呼び出しに応答することはできません。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>グループ番号を割り当て、ユーザーのグループ通話ピックアップを有効にするには

1. 管理者権限を持つ SEFAUtil ツールをインストールしたコンピューターにログオンします。

2. コマンド ラインで、次のコマンドを実行します。

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    たとえば、グループ番号 199 をユーザーに割り当てるには、

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>関連項目

[ユーザーのグループ ピックアップを無効にする](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)