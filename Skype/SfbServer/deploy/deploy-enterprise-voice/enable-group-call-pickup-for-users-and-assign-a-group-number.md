---
title: ユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: '[グループ通話ピックアップ] でユーザーを有効Skype for Business Server エンタープライズ VoIPグループ番号を割り当てる。'
ms.openlocfilehash: 5ebb5d4f2f84133b0c226773fd71c66f687ca5f9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390699"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>ユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当Skype for Business

[グループ通話ピックアップ] でユーザーを有効Skype for Business Server エンタープライズ VoIPグループ番号を割り当てる。

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