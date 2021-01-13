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
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="45c33-103">ユーザーのグループ通話ピックアップを有効にし、Skype for Business でグループ番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="45c33-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="45c33-104">Skype for Business Server のグループ通話ピックアップに対してユーザーを有効エンタープライズ VoIPグループ番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="45c33-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="45c33-105">コール パーク オービット テーブルに通話ピックアップ グループ番号を追加した後、SEFAUtil ツールを使用してグループ番号をユーザーに割り当て、グループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="45c33-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="45c33-106">ハイブリッド展開では、オンラインに配置されているユーザーにグループ通話ピックアップ グループを割り当てない。</span><span class="sxs-lookup"><span data-stu-id="45c33-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="45c33-107">オンラインにホームであるユーザーは、グループ通話ピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="45c33-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="45c33-108">つまり、他のユーザーは通話に応答できません。また、他のユーザーへの呼び出しに応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="45c33-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="45c33-109">グループ番号を割り当て、ユーザーのグループ通話ピックアップを有効にするには</span><span class="sxs-lookup"><span data-stu-id="45c33-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="45c33-110">管理者権限で SEFAUtil ツールをインストールしたコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="45c33-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="45c33-111">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="45c33-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="45c33-112">たとえば、グループ番号 199 をユーザーに割り当てるには、</span><span class="sxs-lookup"><span data-stu-id="45c33-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="45c33-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="45c33-113">See also</span></span>

[<span data-ttu-id="45c33-114">ユーザーのグループ ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="45c33-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

