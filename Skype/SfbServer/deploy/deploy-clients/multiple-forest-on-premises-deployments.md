---
title: Skype Room System の複数フォレストのオンプレミス展開
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: このトピックでは、複数フォレストのオンプレミス環境に Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805747"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="4535a-103">Skype Room System の複数フォレストのオンプレミス展開</span><span class="sxs-lookup"><span data-stu-id="4535a-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="4535a-104">このトピックでは、複数フォレストのオンプレミス環境に Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4535a-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4535a-105">複数のフォレストに展開するには、2014 年 8 月 26 日にリリースExchange Server 2013 CU6 が Skype Room System に必要です。</span><span class="sxs-lookup"><span data-stu-id="4535a-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="4535a-106">Skype Room System の既存のメールボックスを再使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="4535a-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="4535a-107">Skype Room System 用の新しい (古いメールボックスを削除して、作成し再作成する) リソース メールボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4535a-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="4535a-108">メールボックスを削除して失われた会議を復元するには、「削除されたメールボックスを接続または [復元する」を参照してください](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4535a-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="4535a-109">メールボックスを作成した後、メールボックスのSet-CalendarProcessingを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4535a-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="4535a-110">詳細については、単一フォレストのオンプレミス展開の手順 3 . ~ 6. を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4535a-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="4535a-111">Skype Room System 用の Exchange リソース メールボックスを作成した後、単一フォレストのオンプレミス展開で Skype for Business の Skype Room System アカウントを有効にする手順に従って、Skype for Business のアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4535a-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="4535a-112">オプション 1: 新しいリソース メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="4535a-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="4535a-113">複数フォレスト環境に Skype Room System を展開するには:</span><span class="sxs-lookup"><span data-stu-id="4535a-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="4535a-114">Active Directory (認証フォレスト) にリンク ユーザー (LinkedRoomTest) を作成します。</span><span class="sxs-lookup"><span data-stu-id="4535a-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="4535a-115">管理シェルで次のコマンドExchange Server実行します。</span><span class="sxs-lookup"><span data-stu-id="4535a-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="4535a-116">オプション 2: 既存のルーム メールボックスを Skype Room System (リンクされた) リソース メールボックスに変更する</span><span class="sxs-lookup"><span data-stu-id="4535a-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


