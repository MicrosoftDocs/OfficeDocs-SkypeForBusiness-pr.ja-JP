---
title: Skype for Business Server での高解像度写真の使用を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '概要: Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online および Skype for Business Server での高解像度写真の使用を構成します。'
ms.openlocfilehash: f5cc44f9f390c1d3241e7fae68054754ff7b0f76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109803"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="d8627-103">Skype for Business Server での高解像度写真の使用を構成する</span><span class="sxs-lookup"><span data-stu-id="d8627-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="d8627-104">**概要:** Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、Exchange Online および Skype for Business Server での高解像度写真の使用を構成します。</span><span class="sxs-lookup"><span data-stu-id="d8627-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="d8627-105">Skype for Business Server では、写真をユーザーの Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online メールボックスに保存できます。これにより、最大 648 ピクセルの写真サイズを 648 ピクセル×648 ピクセルに設定できます。</span><span class="sxs-lookup"><span data-stu-id="d8627-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="d8627-106">さらに、必要にExchange Server異なる製品で使用するために、これらの写真のサイズを自動的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8627-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="d8627-107">通常、次の 3 つの異なる写真サイズと解像度を意味します。</span><span class="sxs-lookup"><span data-stu-id="d8627-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="d8627-108">64 ピクセル × 64 ピクセル、Active Directory thumbnailPhoto 属性に使用されるサイズ。</span><span class="sxs-lookup"><span data-stu-id="d8627-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="d8627-109">写真を Exchange Server にアップロードすると、Exchange は自動的にその写真の 64 ピクセル バージョンで 64 ピクセルを作成し、ユーザーの thumbnailPhoto 属性を更新します。</span><span class="sxs-lookup"><span data-stu-id="d8627-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="d8627-110">ただし、この逆は true ではありません。Active Directory の thumbnailPhoto 属性を手動で更新した場合、ユーザーの Exchange メールボックスの写真は自動的には更新されません。</span><span class="sxs-lookup"><span data-stu-id="d8627-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="d8627-111">96 ピクセル ×96 ピクセル(Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Skype for Business Web App、Skype for Business で使用)。</span><span class="sxs-lookup"><span data-stu-id="d8627-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="d8627-112">Skype for Business および Skype for Business Web App Skype for Business Web App で使用する場合は、648 ピクセル×648 ピクセル。</span><span class="sxs-lookup"><span data-stu-id="d8627-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d8627-113">リソースがある場合は、648 x 648 の写真をアップロードしてください。任意のアプリケーションで最大解像度と最適な画質Office 2013します。</span><span class="sxs-lookup"><span data-stu-id="d8627-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="d8627-114">サイズが 648 x 648、深度が 24 ビットの各 JPEG 写真では、ファイル サイズは約 240 キロバイトになります。</span><span class="sxs-lookup"><span data-stu-id="d8627-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="d8627-115">つまり、ユーザー写真 4 枚ごとに約 1 メガバイトのディスク領域が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d8627-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="d8627-116">Exchange Web Services を使用してアクセスされる高解像度の写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真のみを更新できます。</span><span class="sxs-lookup"><span data-stu-id="d8627-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="d8627-117">ただし、管理者は、Exchange 管理シェルと次のような一連の Windows PowerShellコマンドを使用して、すべてのユーザーの写真を更新できます。</span><span class="sxs-lookup"><span data-stu-id="d8627-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="d8627-118">前の例の最初のコマンドでは、コマンドレットを使用してファイルの内容を読み取り、C:\Photos\Kenmyer.jpg という名前の変数にデータ `Get-Content` を格納$photo。</span><span class="sxs-lookup"><span data-stu-id="d8627-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="d8627-119">2 番目のコマンドでは、Exchange コマンドレットを使用して写真をアップロードし、その写真を Ken Myer のユーザー アカウント `Set-UserPhoto` に添付します。</span><span class="sxs-lookup"><span data-stu-id="d8627-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8627-120">この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。</span><span class="sxs-lookup"><span data-stu-id="d8627-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="d8627-121">また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8627-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="d8627-122">詳細については、Set-UserPhotoコマンドレットの [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8627-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) for more information</span></span>
  
<span data-ttu-id="d8627-p107">写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d8627-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="d8627-127">新しい写真がユーザー アカウントに割り当てられているか確認するには、Ken Myer は Skype for Business にログオンし、[オプション] を選択し、[マイ ピクチャ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8627-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="d8627-128">新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d8627-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="d8627-129">また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8627-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="d8627-130">管理者が Internet Explorer を使用して写真を表示できますが、ユーザーが Skype for Business で自分の写真を表示できない場合は、Exchange Web Services または Exchange 自動検出サービスとの接続に問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8627-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="d8627-131">この写真を Skype for Business で使用するには、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d8627-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="d8627-132">代わりに、写真がアップロードされ、コマンドレットが実行された後、すぐに `Set-UserPhoto` 写真を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d8627-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>