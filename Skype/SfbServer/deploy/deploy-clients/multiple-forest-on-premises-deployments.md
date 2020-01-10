---
title: 複数フォレストのオンプレミス環境での Skype Room System の展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 13ff6b1dbf1c6ba0cf9c8effddaaae8f097de9ea
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003507"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="c008f-103">複数フォレストのオンプレミス環境での Skype Room System の展開</span><span class="sxs-lookup"><span data-stu-id="c008f-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="c008f-104">このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c008f-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c008f-105">複数のフォレストに展開するために、Skype Room System は2014年8月26日にリリースされた Exchange Server 2013 CU6 を必要とします。</span><span class="sxs-lookup"><span data-stu-id="c008f-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="c008f-106">Skype Room システムの既存のメールボックスを再利用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c008f-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="c008f-107">Skype Room System の新規 (古いメールボックスの削除と再作成) リソースメールボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c008f-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="c008f-108">メールボックスの削除によって失われた会議を復元するには、「[削除されたメールボックスを接続または復元](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c008f-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="c008f-109">メールボックスを作成すると、Set-CalendarProcessing 使用してメールボックスを構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c008f-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="c008f-110">詳細については、「単一フォレストのオンプレミス展開」の手順 3 から 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c008f-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="c008f-111">Skype Room System の Exchange リソースメールボックスを作成した後、「単一フォレストのオンプレミス展開」の「skype for Business の skype Room System アカウントを有効にする」の手順に従って、Skype for Business のアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c008f-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="c008f-112">オプション 1: 新しいリソース メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="c008f-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="c008f-113">複数のフォレスト環境で Skype Room システムを展開するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c008f-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="c008f-114">リンクされているユーザー (LinkedRoomTest) を Active Directory (Authentication Forest) に作成します。</span><span class="sxs-lookup"><span data-stu-id="c008f-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="c008f-115">Exchange Server の管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c008f-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="c008f-116">オプション 2: 既存の会議のメールボックスを Skype Room System (リンク) リソースメールボックスに変更する</span><span class="sxs-lookup"><span data-stu-id="c008f-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


