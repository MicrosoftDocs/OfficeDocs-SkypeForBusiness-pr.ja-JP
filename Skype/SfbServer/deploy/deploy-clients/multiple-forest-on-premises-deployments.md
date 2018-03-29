---
title: 複数フォレストのオンプレミス環境での Skype Room System の展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: b5a0a2615f8174ea5e7d56dcaf0830765365bb48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="f6484-103">複数フォレストのオンプレミス環境での Skype Room System の展開</span><span class="sxs-lookup"><span data-stu-id="f6484-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="f6484-104">このトピックでは、複数フォレストのオンプレミス環境で Skype Room System を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6484-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6484-105">複数のフォレストに配置するには、Skype ルームのシステムには、Exchange Server 2013 CU6 が 2014 年 8 月 26 日にリリースが必要です。</span><span class="sxs-lookup"><span data-stu-id="f6484-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="f6484-106">Skype ルーム システムの既存のメールボックスを再使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f6484-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="f6484-107">使用して、新しい (古いメールボックスを削除して再作成) Skype ルーム システムのリソース メールボックスです。</span><span class="sxs-lookup"><span data-stu-id="f6484-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="f6484-108">メールボックスを削除することによって失われた会議を復元するには、 [[接続] または [削除済みメールボックスの復元](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6484-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="f6484-109">メールボックスを作成すると、Set-CalendarProcessing 使用してメールボックスを構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f6484-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="f6484-110">詳細については、「単一フォレストのオンプレミス展開」の手順 3 から 6 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6484-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="f6484-111">Skype ルーム システム、Exchange リソース メールボックスを作成した後は、設置型展開の 1 つのフォレストでビジネス用の Skype の Skype ルーム システム アカウントの有効化の手順に従って、ビジネスの Skype のアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f6484-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="f6484-112">オプション 1: 新しいリソース メールボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="f6484-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="f6484-113">複数のフォレスト環境では、Skype ルーム システムを展開します。</span><span class="sxs-lookup"><span data-stu-id="f6484-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="f6484-114">リンクされているユーザー (LinkedRoomTest) を Active Directory (Authentication Forest) に作成します。</span><span class="sxs-lookup"><span data-stu-id="f6484-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="f6484-115">Exchange Server の管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6484-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="f6484-116">オプション 2: Skype ルーム システム (リンク) のリソース メールボックスを既存の会議室メールボックスを変更します。</span><span class="sxs-lookup"><span data-stu-id="f6484-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1

```


