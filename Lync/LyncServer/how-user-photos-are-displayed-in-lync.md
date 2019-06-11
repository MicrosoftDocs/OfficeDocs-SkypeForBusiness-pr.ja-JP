---
title: Lync でユーザーの写真を表示する方法
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941c1ab56feea557dfc792ea0af6415dd2a56851
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="45896-102">Lync でユーザーの写真を表示する方法</span><span class="sxs-lookup"><span data-stu-id="45896-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45896-103">_**最終更新日:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="45896-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="45896-104">**概要:** Lync クライアントに表示されるユーザーの写真は、どの Lync 機能を使用しているかによって異なる場合があります。たとえば、会議中や IM チャット中などです。</span><span class="sxs-lookup"><span data-stu-id="45896-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="45896-105">Lync 2010 では、他の Lync ユーザーに対して表示される、Lync プロファイルと共に写真を含める機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="45896-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="45896-106">Lync クライアントで連絡先の写真を表示するかどうかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="45896-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="45896-107">Lync 2013 では、高解像度の写真をユーザー向けにサポートします。</span><span class="sxs-lookup"><span data-stu-id="45896-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="45896-108">このトピックでは、Lync クライアントでユーザーの写真を取得して表示する方法、画像が保存されている場所、各画像ソースの制限事項、さまざまな Lync サービスでユーザーの写真を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="45896-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="45896-109">計画の考慮事項</span><span class="sxs-lookup"><span data-stu-id="45896-109">Planning considerations</span></span>

<span data-ttu-id="45896-110">ユーザー写真のサポートを実装する計画を立てる場合は、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45896-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="45896-111">高解像度ユーザーの写真のサポートでは、ユーザーのメールボックスを Exchange 2013 に配置し、Lync ユーザーアカウントを Lync 2013 プールに置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="45896-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="45896-112">高精細ユーザーの写真は、Lync Server 2013 と Exchange 2013 の両方が使用されている環境でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="45896-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="45896-113">Exchange 2010 上のメールボックスを使用しているユーザーは、常に、ユーザー写真のソースとして AD DS の**thumbnailPhoto**属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="45896-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="45896-114">AD DS から**thumbnailPhoto**属性として保存されているユーザー写真は、外部/フェデレーションの連絡先には表示されません。</span><span class="sxs-lookup"><span data-stu-id="45896-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="45896-115">ユーザーの連絡先の写真が AD DS に保存されている場合、使用される画像ファイルは96×96ピクセルで、100 KB のファイルサイズに制限されています。</span><span class="sxs-lookup"><span data-stu-id="45896-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="45896-116">Lync Server と Exchange Server の間の接続が失われた場合、AD DS からのユーザーの低解像度**thumbnailPhoto**が表示され、内部ユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="45896-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="45896-117">アクティブなスピーカーでビデオが有効になっていない場合、高解像度のユーザー写真が Lync 2013 会議に表示されます。</span><span class="sxs-lookup"><span data-stu-id="45896-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="45896-118">また、ギャラリーのサムネイル写真の上にマウスを移動すると、高解像度の写真が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45896-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="45896-119">Lync 2010 でのユーザーの写真</span><span class="sxs-lookup"><span data-stu-id="45896-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="45896-120">Lync 2010 クライアントでは、次の2つのオプションのいずれかを選択して、自分のプロファイルの写真を表示したり、**既定の会社の画像**を表示したり、 **web アドレスの画像を表示**したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="45896-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="45896-121">既定の企業の画像</span><span class="sxs-lookup"><span data-stu-id="45896-121">Default corporate picture</span></span>

<span data-ttu-id="45896-122">**既定の企業図**オプションを選択すると、Lync は Active Directory ドメインサービスから表示した写真を取得します。</span><span class="sxs-lookup"><span data-stu-id="45896-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="45896-123">使用される画像は、Active Directory ドメインサービスの**thumbnailPhoto**属性の値として定義されている画像です。</span><span class="sxs-lookup"><span data-stu-id="45896-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="45896-124">これは、Outlook で画像を表示するために Exchange で使用されるファイルと同じです。</span><span class="sxs-lookup"><span data-stu-id="45896-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="45896-125">Active Directory ドメインサービスからの画像の使用に関する考慮事項には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="45896-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="45896-126">96ピクセルで最大96ピクセルのサイズの画像のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="45896-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="45896-127">画像のファイルサイズは、100 KB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="45896-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="45896-128">既定では、ユーザーは**thumbnailPhoto**属性に使用される画像を変更できますが、Lync クライアントから直接変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="45896-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="45896-129">Active Directory ドメインサービスを使用して、これを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="45896-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="45896-130">Active Directory ドメインサービスに保存されている画像は、フェデレーションされた連絡先である場合でも、組織外の連絡先には表示されません。</span><span class="sxs-lookup"><span data-stu-id="45896-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="45896-131">大規模な組織では、多数のユーザーのために画像を保存して取得すると、Active Directory ドメインサービスのデータベースのサイズとパフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45896-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="45896-132">限られた画像サイズとファイルサイズは、低解像度の画像のみを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="45896-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="45896-133">Active Directory ドメインサービスでユーザーの写真を管理する方法</span><span class="sxs-lookup"><span data-stu-id="45896-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="45896-134">ユーザーは、Lync 2010 クライアントを介して、Active Directory ドメインサービスプロファイルで使用されている画像を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="45896-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="45896-135">使用できる場合は、次のいずれかのオプションを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="45896-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="45896-136">**Sharepoint server**   ユーザーは、sharepoint サーバー上の [個人用サイト] に写真をアップロードし、 [sharepoint でプロファイルの同期を構成](http://go.microsoft.com/fwlink/p/?linkid=507466)して、その写真を Active Directory ドメインの**thumbnailPhoto**属性と同期させることができます。サービス.</span><span class="sxs-lookup"><span data-stu-id="45896-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="45896-137">**公開されているアクセシビリティ**   の高い url に保存されている写真ユーザーは、使用する画像の公開可能な url を指定してユーザーの写真を構成できます。</span><span class="sxs-lookup"><span data-stu-id="45896-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="45896-138">画像には、パスワードなしでアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45896-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="45896-139">指定した web アドレスに保存されている画像は、プレゼンス情報の連絡先カードカテゴリを通じて他のユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="45896-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="45896-140">Lync クライアントでユーザーの写真を表示する必要がある場合は、指定した web アドレスから画像を取得します。</span><span class="sxs-lookup"><span data-stu-id="45896-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="45896-141">**Windows PowerShell**   管理者の exchange 2010 コマンドレットでは、thumbnailPhoto 属性を管理するために、exchange 2010 の管理シェルで、 \*\*\*\* の[インポートのプロパティ](http://go.microsoft.com/fwlink/p/?linkid=507468)レットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="45896-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="45896-142">Exchange 2010 コマンドレットを使用して画像をインポートすると、ファイルサイズは 10 KB に制限されます。</span><span class="sxs-lookup"><span data-stu-id="45896-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="45896-143">**サードパーティのツール**   ユーザーは、自分の写真だけを**thumbnailPhoto**属性にアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="45896-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="45896-144">Web アドレスの画像を表示する</span><span class="sxs-lookup"><span data-stu-id="45896-144">Show a picture from a web address</span></span>

<span data-ttu-id="45896-145">[ **Web アドレスから画像を表示**する] オプションを選ぶと、lync では、入力したアドレスに画像が表示され、lync でユーザー写真の画像が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45896-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="45896-146">Web アドレスからの画像の使用に関する考慮事項には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="45896-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="45896-147">ファイルサイズの制限は、[新しい-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463)コマンドレットで定義された、クライアントポリシーの**Maxphotosizekb**属性によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="45896-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="45896-148">既定のサイズ制限は、30 KB です。</span><span class="sxs-lookup"><span data-stu-id="45896-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="45896-149">最大値は 100 KB です。</span><span class="sxs-lookup"><span data-stu-id="45896-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="45896-150">画像の解像度には制限はありませんが、サイズ制限を超えている画像ファイルを使用しようとしても、Lync クライアントにダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="45896-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="45896-151">この値を0に設定すると、すべてのユーザーの写真を Lync で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="45896-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="45896-152">Web アドレスからのユーザーの写真は、フェデレーションされた外部の連絡先から見ることができます。</span><span class="sxs-lookup"><span data-stu-id="45896-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="45896-153">クライアントポリシーコマンドレットを使用してユーザーの写真を管理する</span><span class="sxs-lookup"><span data-stu-id="45896-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="45896-154">Lync Server 2010 では、クライアントポリシー設定は CsClientPolicy コマンドレットで構成されています。</span><span class="sxs-lookup"><span data-stu-id="45896-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="45896-155">構成済みのポリシー設定は、インバンドプロビジョニングを通じてクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="45896-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="45896-156">ユーザーの写真エクスペリエンスを決定する CsClientPolicy コマンドレットの2つのパラメーターは、 **DisplayPhoto**と**Maxphotosizekb**です。</span><span class="sxs-lookup"><span data-stu-id="45896-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="45896-157">**DisplayPhoto**と**Maxphotosizekb**の対応するインバンドプロビジョニングパラメーターは、 **PhotoUsage**という名前です。</span><span class="sxs-lookup"><span data-stu-id="45896-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="45896-158">**PhotoUsage**パラメーターの値は、 **endpointConfiguration** **provisionGroup**経由でクライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="45896-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="45896-159">詳細については[、「クライアントポリシーと設定の概要](http://go.microsoft.com/fwlink/?linkid=507470)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45896-159">See [Overview of Client Policies and Settings](http://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="45896-160">**DisplayPhoto**パラメーターの値は、ユーザーの写真イメージのソースを決定します。</span><span class="sxs-lookup"><span data-stu-id="45896-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="45896-161">サポートされている値は、次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="45896-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45896-162">DisplayPhoto パラメーター値</span><span class="sxs-lookup"><span data-stu-id="45896-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="45896-163">画像ソース</span><span class="sxs-lookup"><span data-stu-id="45896-163">Image source</span></span></th>
<th><span data-ttu-id="45896-164">Lync 2010 クライアントの設定</span><span class="sxs-lookup"><span data-stu-id="45896-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45896-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="45896-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="45896-166">なし</span><span class="sxs-lookup"><span data-stu-id="45896-166">none</span></span></p></td>
<td><p><span data-ttu-id="45896-167"><strong>自分の写真を表示しない</strong></span><span class="sxs-lookup"><span data-stu-id="45896-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45896-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="45896-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="45896-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="45896-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="45896-170"><strong>既定の企業の画像</strong></span><span class="sxs-lookup"><span data-stu-id="45896-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45896-171">すべての写真</span><span class="sxs-lookup"><span data-stu-id="45896-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="45896-172">Web アドレス</span><span class="sxs-lookup"><span data-stu-id="45896-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="45896-173"><strong>Web アドレスの画像を表示する</strong></span><span class="sxs-lookup"><span data-stu-id="45896-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="45896-174">Lync 2010 クライアントで写真を取得する方法</span><span class="sxs-lookup"><span data-stu-id="45896-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="45896-175">Lync 2010 では、ユーザーの写真はアドレス帳サービスによってサーバー上で管理されます。</span><span class="sxs-lookup"><span data-stu-id="45896-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="45896-176">Lync クライアントは、最初に、配布リスト展開 web サービスを通じて公開されるサーバー上のアドレス帳 Web クエリ (ABWQ) サービスを照会することによって、ユーザーの写真を取得します。</span><span class="sxs-lookup"><span data-stu-id="45896-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="45896-177">クライアントはイメージファイルを受け取り、ユーザーのキャッシュにコピーして、表示する必要があるたびにイメージをダウンロードしないようにします。</span><span class="sxs-lookup"><span data-stu-id="45896-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="45896-178">クエリから返された属性値は、ユーザーのキャッシュされたアドレス帳サービスエントリにも格納されます。</span><span class="sxs-lookup"><span data-stu-id="45896-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="45896-179">アドレス帳サービスは、キャッシュされているすべての画像を24時間ごとに削除します。つまり、サーバー上のキャッシュで新しいユーザーの画像が更新されるまでに最大24時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45896-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="45896-180">[CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)コマンドレットを使用して、キャッシュを強制的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="45896-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="45896-181">プレゼンス状態に含まれているユーザーの写真にも、新しい画像が利用可能かどうかを判断するために Lync クライアントによって使用されるハッシュ値が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="45896-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="45896-182">プレゼンス状態で使用される画像ファイルへの変更がクライアントに自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="45896-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="45896-183">写真は GalContacts データベースに保存されていないため、ユーザーの写真をダウンロードしても、クライアントポリシー (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">CsClientPolicy</A>) の<STRONG>addressbookavailability</STRONG>の設定に依存していません。</span><span class="sxs-lookup"><span data-stu-id="45896-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="45896-184">ABWQ サービスへのクエリには、次の属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45896-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="45896-185">**Photohash**の写真が変更されたかどうかを判断するために使用される、バイナリ写真データのハッシュ値。   </span><span class="sxs-lookup"><span data-stu-id="45896-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="45896-186">\*\*\*\*   サーバーに保存されている画像ファイルへの相対パスを PhotoRelPath します。</span><span class="sxs-lookup"><span data-stu-id="45896-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="45896-187">**[Photosize**   ] 画像ファイルのサイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="45896-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="45896-188">**タイムスタンプ**   イメージファイルが最後にサーバーからダウンロードされ、クライアントキャッシュにコピーされた日時です。</span><span class="sxs-lookup"><span data-stu-id="45896-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="45896-189">次に、画像ファイルを取得した後、Lync 2010 クライアントは、クエリから返された属性値と、インバンドプロビジョニングからクライアントが受け取った属性値とを比較して、それらが異なるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="45896-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="45896-190">値が異なる場合、クライアントは、サインインしたユーザーの画像ファイルを HTTP GET 要求で取得します。</span><span class="sxs-lookup"><span data-stu-id="45896-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="45896-191">さらに、クライアントは、キャッシュされたバージョンのイメージファイルが作成された時点から24時間ごとにサーバーに確認して、サーバー上の**Photohash**属性の値とクライアント上の値とを比較します。</span><span class="sxs-lookup"><span data-stu-id="45896-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="45896-192">値が異なる場合は、画像ファイルが変更されていることがクライアントに認識されます。</span><span class="sxs-lookup"><span data-stu-id="45896-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="45896-193">更新された画像ファイルを取得するために、クライアントはもう一度 ABWQ サービスを照会して、クライアントキャッシュのイメージファイルをサーバー上の画像ファイルに更新します。これにより、クライアントキャッシュ内のファイルの**タイムスタンプ**もリセットされます。</span><span class="sxs-lookup"><span data-stu-id="45896-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="45896-194">次に示すのは、ABWQ サービスへのクエリに対する応答の例です。</span><span class="sxs-lookup"><span data-stu-id="45896-194">The following is an example response to a query to the ABWQ service:</span></span>

    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="45896-195">Lync 2013 でのユーザーの写真</span><span class="sxs-lookup"><span data-stu-id="45896-195">User photos in Lync 2013</span></span>

<span data-ttu-id="45896-196">Lync 2013 では、ユーザー写真用の高解像度の画像のサポートが導入されました。</span><span class="sxs-lookup"><span data-stu-id="45896-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="45896-197">Lync 2013 には、ユーザーの写真を Exchange 2013 上のユーザーのメールボックスに保存する機能もサポートされています。これにより、Lync 2010 に含まれる画像の解像度とサイズの制限が削除されます。</span><span class="sxs-lookup"><span data-stu-id="45896-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="45896-198">Lync 2013 でのユーザーの写真は、最大 20 MB のファイルサイズで、648ピクセルで最大648ピクセルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="45896-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="45896-199">Lync 2013 の高解像度の写真は、Exchange 2013 のユーザーのメールボックスに配置されている必要があります。また、Lync 2013 クライアントでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="45896-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="45896-200">Exchange との統合により、2013バージョンの Lync、Exchange、および SharePoint の Oauth という新しい承認フレームワークが利用されます。</span><span class="sxs-lookup"><span data-stu-id="45896-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="45896-201">展開で Exchange 2013 が使用されていない場合、ユーザーの写真のサポートは Lync 2010 と同じです。</span><span class="sxs-lookup"><span data-stu-id="45896-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="45896-202">ただし、使用する写真を選ぶためのユーザーオプションは、Lync 2013 クライアントでは異なります。</span><span class="sxs-lookup"><span data-stu-id="45896-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="45896-203">Lync 2013 クライアントでは、ユーザーは [**写真を非表示**にする] または [**マイピクチャを表示**する] のいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="45896-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="45896-204">[ **Web サイトの画像を表示**する] オプションは既定では利用できませんが、クライアントポリシーを割り当てることで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="45896-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="45896-205">写真を表示しない</span><span class="sxs-lookup"><span data-stu-id="45896-205">Hide my picture</span></span>

<span data-ttu-id="45896-206">ユーザー写真の設定は、Lync 2013 の [**オプション**] ダイアログにあります。</span><span class="sxs-lookup"><span data-stu-id="45896-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="45896-207">[自分の**写真を表示**しない] を選ぶと、lync クライアントではユーザーの写真は表示されませんが、自分の写真は連絡先カードと lync の外部に表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="45896-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="45896-208">自分の写真を表示</span><span class="sxs-lookup"><span data-stu-id="45896-208">Show my picture</span></span>

<span data-ttu-id="45896-209">**[自分の写真を表示**する] オプションを選択すると、lync クライアントおよび lync での会話で他のユーザーにユーザーの写真が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45896-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="45896-210">使用されている画像は、AD DS に保存されているものです。</span><span class="sxs-lookup"><span data-stu-id="45896-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="45896-211">Web サイトの画像を表示する</span><span class="sxs-lookup"><span data-stu-id="45896-211">Show a picture from a website</span></span>

<span data-ttu-id="45896-212">クライアントポリシーを有効にするように設定した後、[ **web サイトの画像を表示**する] オプションが Lync 2013 で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="45896-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="45896-213">クライアントバージョンは、Lync 累積更新プログラムと共にインストールされている15.0.4535.1002 よりも新しいバージョンである必要があります。 [2013 年11月](http://go.microsoft.com/fwlink/p/?linkid=509908)。</span><span class="sxs-lookup"><span data-stu-id="45896-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="45896-214">クライアントの変更を確認するには、ユーザーがもう一度ログアウトしてから再びログインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="45896-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="45896-215">Lync Server 管理シェルで[set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)ポリシーを実行して、 **web サイトの設定から画像が表示**されるようにクライアントポリシーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="45896-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="45896-216">展開内のすべてのユーザーに対してグローバルにポリシーを設定する方法を示すコマンドレットの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="45896-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```
    $po.PolicyEntry.Add($pe)
   ```

   ```
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="45896-217">ユーザーのメールボックスに画像がアップロードされると、Exchange では、クライアントアプリケーションで使用できる画像の低解像度バージョンが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="45896-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="45896-218">また、ユーザーの写真は、AD DS でも更新されます。</span><span class="sxs-lookup"><span data-stu-id="45896-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="45896-219">AD DS でイメージファイルが更新されると、48 x 48 ピクセルのイメージが作成され、AD DS の thumbnailPhoto に使用されます。</span><span class="sxs-lookup"><span data-stu-id="45896-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="45896-220">既存の画像はすべて置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="45896-220">Any existing image is replaced.</span></span> <span data-ttu-id="45896-221">そのため、96 x 96 のイメージを AD DS に追加した場合は、新しい 48 x 48 イメージによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="45896-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="45896-222">これは重要なのは、Lync 2010 クライアントを使用している環境内にユーザーがいて、ユーザーの写真が AD DS から取得されるためです。</span><span class="sxs-lookup"><span data-stu-id="45896-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="45896-223">組織内に Lync 2010 クライアントがある場合は、96 x 96 ピクセルのイメージをインポートして、AD DS によって作成されたものを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="45896-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="45896-224">Lync 2013 でのユーザー写真のサポート</span><span class="sxs-lookup"><span data-stu-id="45896-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="45896-225">Lync 2013 では、次の表に示すように、ユーザーの写真で3つの画像解像度がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="45896-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="45896-226">使用される画像は、Lync ユーザーに割り当てられているクライアントポリシーの設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="45896-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="45896-227">詳細については、このトピックの「クライアントポリシーコマンドレットを使用してユーザーの写真を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45896-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45896-228">画像の解像度 (ピクセル)</span><span class="sxs-lookup"><span data-stu-id="45896-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="45896-229">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="45896-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45896-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="45896-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="45896-231">高解像度の画像が選択されていない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="45896-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45896-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="45896-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="45896-233">Outlook Web App および Outlook 2013 で使用</span><span class="sxs-lookup"><span data-stu-id="45896-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45896-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="45896-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="45896-235">Lync 2013 デスクトップクライアントおよび Lync 2013 Web アプリで使用</span><span class="sxs-lookup"><span data-stu-id="45896-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="45896-236">Exchange 2013 でメールボックスが有効になっているユーザーは、高解像度の写真など、Outlook Web Access または Lync 2013 クライアントオプションを使用して、別の画像をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="45896-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="45896-237">使用する画像の推奨設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="45896-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="45896-238">\*\*\*\*   648 x 648 ピクセルの画像解像度</span><span class="sxs-lookup"><span data-stu-id="45896-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="45896-239">**色深度**   24 ビット</span><span class="sxs-lookup"><span data-stu-id="45896-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="45896-240">**画像ファイルのサイズ**   が最大 20 MB</span><span class="sxs-lookup"><span data-stu-id="45896-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="45896-241">**ファイル形式**   JPEG</span><span class="sxs-lookup"><span data-stu-id="45896-241">**File format**   JPEG</span></span>

<span data-ttu-id="45896-242">648ピクセル x 648 ピクセルの標準的な24ビット JPEG 画像のファイルサイズは約 240 KB であるため、4ユーザー写真ごとに 1 MB の記憶領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="45896-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

