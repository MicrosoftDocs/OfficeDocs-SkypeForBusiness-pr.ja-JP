---
title: Skype for Business でユーザーのグループ通話のピックアップを有効にし、グループ番号を割り当てる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Skype for Business Server Enterprise Voice でグループ通話のピックアップを有効にして、グループ番号を割り当てることができます。
ms.openlocfilehash: 78bdd78bf7e5bb3a9438a60b54a89664d22666ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240349"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Skype for Business でユーザーのグループ通話のピックアップを有効にし、グループ番号を割り当てる

Skype for Business Server Enterprise Voice でグループ通話のピックアップを有効にして、グループ番号を割り当てることができます。

通話の集配グループ番号をコールパークの軌道テーブルに追加した後は、SEFAUtil ツールを使用してグループ番号をユーザーに割り当て、グループ通話のピックアップを有効にすることができます。

> [!NOTE]
> ハイブリッド展開では、オンラインのユーザーにグループの通話ピックアップグループを割り当てないでください。 自宅のユーザーはグループ通話のピックアップに参加できません。 つまり、オンラインに所属するユーザーへの呼び出しを他のユーザーが応答することや、他のユーザーへの呼び出しをオンラインに所属するユーザーが応答することはできません。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>グループ番号を割り当てて、ユーザーに対してグループ通話のピックアップを有効にするには

1. SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。

2. コマンド ラインで、次のコマンドを実行します。

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    たとえば、グループ番号 199 をユーザーに割り当てるには

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>関連項目

[Disable Group Pickup for Users](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

