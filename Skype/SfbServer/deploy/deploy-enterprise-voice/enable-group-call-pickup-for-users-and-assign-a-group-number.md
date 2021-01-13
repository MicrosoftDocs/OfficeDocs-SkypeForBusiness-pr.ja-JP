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
description: Skype for Business Server のグループ通話ピックアップに対してユーザーを有効エンタープライズ VoIPグループ番号を割り当てる。
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830967"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>ユーザーのグループ通話ピックアップを有効にし、Skype for Business でグループ番号を割り当てる

Skype for Business Server のグループ通話ピックアップに対してユーザーを有効エンタープライズ VoIPグループ番号を割り当てる。

コール パーク オービット テーブルに通話ピックアップ グループ番号を追加した後、SEFAUtil ツールを使用してグループ番号をユーザーに割り当て、グループ通話ピックアップを有効にします。

> [!NOTE]
> ハイブリッド展開では、オンラインに配置されているユーザーにグループ通話ピックアップ グループを割り当てない。 オンラインにホームであるユーザーは、グループ通話ピックアップに参加できません。 つまり、他のユーザーは通話に応答できません。また、他のユーザーへの呼び出しに応答することはできません。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>グループ番号を割り当て、ユーザーのグループ通話ピックアップを有効にするには

1. 管理者権限で SEFAUtil ツールをインストールしたコンピューターにログオンします。

2. コマンド ラインで、次のコマンドを実行します。

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    たとえば、グループ番号 199 をユーザーに割り当てるには、

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>関連項目

[ユーザーのグループ ピックアップを無効にする](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

