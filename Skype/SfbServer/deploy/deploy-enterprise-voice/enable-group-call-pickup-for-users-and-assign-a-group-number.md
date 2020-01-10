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
ms.openlocfilehash: 8ded9fbf7e9a9c8034684c1477c6aad92bfc9e5f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002547"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="95923-103">Skype for Business でユーザーのグループ通話のピックアップを有効にし、グループ番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="95923-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="95923-104">Skype for Business Server Enterprise Voice でグループ通話のピックアップを有効にして、グループ番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="95923-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="95923-105">通話の集配グループ番号をコールパークの軌道テーブルに追加した後は、SEFAUtil ツールを使用してグループ番号をユーザーに割り当て、グループ通話のピックアップを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="95923-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="95923-106">ハイブリッド展開では、オンラインのユーザーにグループの通話ピックアップグループを割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="95923-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="95923-107">自宅のユーザーはグループ通話のピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="95923-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="95923-108">つまり、オンラインに所属するユーザーへの呼び出しを他のユーザーが応答することや、他のユーザーへの呼び出しをオンラインに所属するユーザーが応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="95923-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="95923-109">グループ番号を割り当てて、ユーザーに対してグループ通話のピックアップを有効にするには</span><span class="sxs-lookup"><span data-stu-id="95923-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="95923-110">SEFAUtil ツールをインストールしたコンピューターに管理者権限でログオンします。</span><span class="sxs-lookup"><span data-stu-id="95923-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="95923-111">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95923-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="95923-112">たとえば、グループ番号 199 をユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="95923-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="95923-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="95923-113">See also</span></span>

[<span data-ttu-id="95923-114">Disable Group Pickup for Users</span><span class="sxs-lookup"><span data-stu-id="95923-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

