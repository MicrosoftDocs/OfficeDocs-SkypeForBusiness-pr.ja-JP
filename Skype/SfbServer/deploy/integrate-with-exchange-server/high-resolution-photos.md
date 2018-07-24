---
title: ビジネス サーバー用の Skype の高解像度の写真の使用を構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '概要: ビジネス サーバーの 2016 の Exchange Server や Exchange Server 2013 と Skype の高解像度の写真の使用を構成します。'
ms.openlocfilehash: 224c8dc238d8427deddc706b883614fd04c9b133
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21007238"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="6d022-103">ビジネス サーバー用の Skype の高解像度の写真の使用を構成します。</span><span class="sxs-lookup"><span data-stu-id="6d022-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="6d022-104">**の概要:** 2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバーの高解像度の写真の使用を構成します。</span><span class="sxs-lookup"><span data-stu-id="6d022-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="6d022-105">ビジネス サーバーの Skype では、メールボックスの [ユーザーの 2016 の Exchange Server や Exchange Server 2013 できる写真のサイズの最大の 648 648 ピクセル ピクセル写真を格納できます。</span><span class="sxs-lookup"><span data-stu-id="6d022-105">In Skype for Business Server photos can be stored in a user's Exchange Server 2016 or Exchange Server 2013 mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="6d022-106">さらに、Exchange Server に自動的にサイズを変更できますこれらの写真のさまざまな製品で使用するため必要に応じて。</span><span class="sxs-lookup"><span data-stu-id="6d022-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="6d022-107">通常次の 3 つの別の写真のサイズおよび解像度を意味します。</span><span class="sxs-lookup"><span data-stu-id="6d022-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="6d022-108">64 × 64 ピクセル、thumbnailPhoto の Active Directory 属性を使用するサイズです。</span><span class="sxs-lookup"><span data-stu-id="6d022-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="6d022-109">Exchange Server に写真をアップロードする場合 Exchange が自動的にその写真の 64 ピクセルのバージョンで 64 ピクセルを作成およびユーザーの thumbnailPhoto の属性を更新します。</span><span class="sxs-lookup"><span data-stu-id="6d022-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="6d022-110">ただし、逆は真ではありません: Active Directory 内の thumbnailPhoto 属性を手動で更新する場合は、ユーザーの Exchange メールボックスにある写真に自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="6d022-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="6d022-111">Microsoft Outlook 2013 の Web アプリケーション、Microsoft Outlook 2013、Skype のビジネス Web アプリケーション、およびビジネス用の Skype で使用するための 96 ピクセルで 96 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="6d022-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="6d022-112">648 648 のピクセルのピクセルを使用して、Skype のビジネスおよび Skype のビジネス Web アプリケーションの Skype のビジネス Web アプリケーションの。</span><span class="sxs-lookup"><span data-stu-id="6d022-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6d022-113">リソースがある場合は、648 648 x 画像をアップロードすることをお勧め最大解像度と任意の Office 2013 アプリケーションで最適な画質を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d022-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="6d022-114">648 648 x のサイズと深さが 24 ビットの JPEG 写真のそれぞれは、約 240 キロバイトのファイルのサイズになります。</span><span class="sxs-lookup"><span data-stu-id="6d022-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="6d022-115">つまり、すべての 4 つのユーザーの写真の約 1m バイトのディスク領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="6d022-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="6d022-116">Outlook 2013 Web アプリケーションを実行しているユーザーが Exchange Web サービスを使用してアクセスされる、高解像度の写真をアップロードします。自分の写真を更新するのには許可されているだけです。</span><span class="sxs-lookup"><span data-stu-id="6d022-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="6d022-117">ただし、管理者は、Exchange 管理シェルは、一連の Windows PowerShell コマンドを次のようなを使用してすべてのユーザーの写真を更新できます。</span><span class="sxs-lookup"><span data-stu-id="6d022-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData -Preview $photo -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="6d022-118">前の例の最初のコマンドを使用して、 `Get-Content` $photo という名前のコマンドレットには、C:\Photos\Kenmyer.jpg ファイルの内容を読むし、そのデータを変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="6d022-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="6d022-119">2 番目のコマンドでは、Exchange コマンドレットの`Set-UserPhoto`を使用して写真をアップロードし、Ken Myer のユーザー アカウントにその写真を添付します。</span><span class="sxs-lookup"><span data-stu-id="6d022-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d022-120">この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。</span><span class="sxs-lookup"><span data-stu-id="6d022-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="6d022-121">また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d022-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="6d022-122">セット UserPhoto コマンドレットのドキュメントを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)の詳細について</span><span class="sxs-lookup"><span data-stu-id="6d022-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) for more information</span></span>
  
<span data-ttu-id="6d022-p107">写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6d022-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="6d022-127">新しい写真がユーザー アカウントに割り当てられていることを確認するには、Ken Myer にログオンできる Skype のビジネス、**オプション**の選択]、および [**マイ ピクチャ**。</span><span class="sxs-lookup"><span data-stu-id="6d022-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="6d022-128">新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="6d022-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="6d022-129">また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d022-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

<span data-ttu-id="6d022-130">管理者は、Internet Explorer を使用して写真を表示できますが、ユーザーは、ビジネスの Skype で自分の写真を表示できない場合は、Exchange Web サービスまたは Exchange 自動検出サービス接続の問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d022-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="6d022-131">またビジネス用の Skype でこの写真を利用するのには追加構成は必要ないことです。</span><span class="sxs-lookup"><span data-stu-id="6d022-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="6d022-132">代わりに、写真すぐが表示されますが、アップロードされた後、および`Set-UserPhoto`コマンドレットが実行されています。</span><span class="sxs-lookup"><span data-stu-id="6d022-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>
