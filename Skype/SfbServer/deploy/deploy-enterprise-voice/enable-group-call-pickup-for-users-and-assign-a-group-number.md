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
ms.openlocfilehash: 5a4173a16a40557742a7cdbd47edb917f89b4737
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006521"
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

[ユーザーに対して無効にするグループ ピックアップ](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

