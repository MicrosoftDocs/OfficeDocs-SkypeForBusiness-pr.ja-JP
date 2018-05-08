---
title: Skype for Business 2015 でのユーザーに対するグループ通話ピックアップの有効化とグループ番号の割り当て
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
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
ms.openlocfilehash: ce360bc1f66f3e7b55d3c0f8ea9e392d957f25ea
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business-2015"></a><span data-ttu-id="6b866-103">Skype for Business 2015 でのユーザーに対するグループ通話ピックアップの有効化とグループ番号の割り当て</span><span class="sxs-lookup"><span data-stu-id="6b866-103">Enable Group Call Pickup for users and assign a group number in Skype for Business 2015</span></span>
 
<span data-ttu-id="6b866-104">Skype でグループを呼び出すのピックアップのためビジネス サーバーのエンタープライズ VoIP に対してユーザーを有効にして、グループ番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6b866-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>
  
<span data-ttu-id="6b866-105">コール ピックアップ グループの番号をコール パークの回り込みテーブルに追加した後は、ユーザーにグループ番号を割り当てるし、それらのグループを呼び出すピックアップを有効にするのに SEFAUtil ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b866-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b866-106">ハイブリッド展開では、グループのコール ピックアップ グループに割り当てないオンラインが置かれているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="6b866-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="6b866-107">オンラインが置かれているユーザーは、コール ピックアップのグループに参加できません。</span><span class="sxs-lookup"><span data-stu-id="6b866-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="6b866-108">つまり、オンラインに所属するユーザーへの呼び出しを他のユーザーが応答することや、他のユーザーへの呼び出しをオンラインに所属するユーザーが応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b866-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span> 
  
### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="6b866-109">グループ番号を割り当てるし、ユーザーのグループを呼び出すピックアップを有効にするには</span><span class="sxs-lookup"><span data-stu-id="6b866-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="6b866-110">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="6b866-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>
    
2. <span data-ttu-id="6b866-111">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b866-111">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="6b866-112">たとえば、グループ番号 199 をユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="6b866-112">For example, to assign group number 199 to a user:</span></span>
    
   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 
   ```

## <a name="see-also"></a><span data-ttu-id="6b866-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b866-113">See also</span></span>

#### 

[<span data-ttu-id="6b866-114">ユーザーに対して無効にするグループ ピックアップ</span><span class="sxs-lookup"><span data-stu-id="6b866-114">Disable Group Pickup for Users</span></span>](http://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

