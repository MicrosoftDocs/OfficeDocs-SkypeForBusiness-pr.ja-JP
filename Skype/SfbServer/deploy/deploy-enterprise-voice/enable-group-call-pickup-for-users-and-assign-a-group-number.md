---
title: ユーザーのグループを呼び出すピックアップを有効にして、ビジネスの Skype でグループ番号を割り当てる
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Skype でグループを呼び出すのピックアップのためビジネス サーバーのエンタープライズ VoIP に対してユーザーを有効にして、グループ番号を割り当てます。
ms.openlocfilehash: e182919023aab7757f975cbdccc509a0b62a77b9
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260007"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>ユーザーのグループを呼び出すピックアップを有効にして、ビジネスの Skype でグループ番号を割り当てる

Skype でグループを呼び出すのピックアップのためビジネス サーバーのエンタープライズ VoIP に対してユーザーを有効にして、グループ番号を割り当てます。

コール ピックアップ グループの番号をコール パークの回り込みテーブルに追加した後は、ユーザーにグループ番号を割り当てるし、それらのグループを呼び出すピックアップを有効にするのに SEFAUtil ツールを使用します。

> [!NOTE]
> ハイブリッド展開では、グループのコール ピックアップ グループに割り当てないオンラインが置かれているユーザーです。 オンラインが置かれているユーザーは、コール ピックアップのグループに参加できません。 つまり、オンラインに所属するユーザーへの呼び出しを他のユーザーが応答することや、他のユーザーへの呼び出しをオンラインに所属するユーザーが応答することはできません。

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>グループ番号を割り当てるし、ユーザーのグループを呼び出すピックアップを有効にするには

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

[ユーザーに対して無効にするグループ ピックアップ](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

