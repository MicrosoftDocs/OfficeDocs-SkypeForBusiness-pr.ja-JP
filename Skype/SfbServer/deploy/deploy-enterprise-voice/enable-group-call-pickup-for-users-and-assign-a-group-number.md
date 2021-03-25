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
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="26af9-103">ユーザーのグループ通話ピックアップを有効にし、Skype for Business でグループ番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="26af9-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="26af9-104">Skype for Business Server のグループ通話ピックアップでユーザーを有効エンタープライズ VoIPグループ番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="26af9-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="26af9-105">コール パーク オービット テーブルに通話ピックアップ グループ番号を追加した後、SEFAUtil ツールを使用してグループ番号をユーザーに割り当て、グループ通話ピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="26af9-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="26af9-106">ハイブリッド展開では、グループ通話ピックアップ グループをオンラインのユーザーに割り当てない。</span><span class="sxs-lookup"><span data-stu-id="26af9-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="26af9-107">オンラインに参加しているユーザーは、グループ通話ピックアップに参加できません。</span><span class="sxs-lookup"><span data-stu-id="26af9-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="26af9-108">つまり、他のユーザーが通話に応答することはできません。また、他のユーザーへの呼び出しに応答することはできません。</span><span class="sxs-lookup"><span data-stu-id="26af9-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="26af9-109">グループ番号を割り当て、ユーザーのグループ通話ピックアップを有効にするには</span><span class="sxs-lookup"><span data-stu-id="26af9-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="26af9-110">管理者権限を持つ SEFAUtil ツールをインストールしたコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="26af9-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="26af9-111">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="26af9-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="26af9-112">たとえば、グループ番号 199 をユーザーに割り当てるには、</span><span class="sxs-lookup"><span data-stu-id="26af9-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="26af9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="26af9-113">See also</span></span>

[<span data-ttu-id="26af9-114">ユーザーのグループ ピックアップを無効にする</span><span class="sxs-lookup"><span data-stu-id="26af9-114">Disable Group Pickup for Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)