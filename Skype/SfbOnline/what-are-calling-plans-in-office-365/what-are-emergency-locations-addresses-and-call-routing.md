---
title: "緊急の場所、住所、その通話をルーティングする機能とは"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "緊急アドレス、場所、および緊急の通話をルーティングする機能とは何か」と「計画やユーザーに割り当てる方法について説明します。 "
ms.openlocfilehash: 35553da49cbaffde1a960ce83550b6fc4ce3ef07
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a><span data-ttu-id="8712d-103">緊急の場所、住所、その通話をルーティングする機能とは</span><span class="sxs-lookup"><span data-stu-id="8712d-103">What are emergency locations, addresses and call routing?</span></span>

<span data-ttu-id="8712d-p101">Office 365 のプランの呼び出しを設定するときにことが必要なすべてのユーザーを電話番号を取得するかするとき、または電話番号ごとに割り当てられた緊急アドレス緊急通話をサポートするユーザーに割り当てられたそのします。電話番号、緊急のアドレスを割り当てる、前に緊急アドレスを作成および検証される必要があります。入力規則により、緊急のアドレスが認識されると、緊急サービスで使用できる正しい形式であります。必要に応じて、ユーザーの他の特定の場所を提供する緊急アドレス内の場所を追加できます。たとえば、緊急の場所では、フロア、翼、または office 緊急の特定のアドレスにリンクされている場合があります。緊急のアドレスが検証されるにも関わらず、場所がありません。</span><span class="sxs-lookup"><span data-stu-id="8712d-p101">When you are configuring Calling Plans in Office 365, it's required that an emergency address be assigned to each telephone number when you either get the phone number or when its assigned to a user to support emergency calling. Before assigning an emergency address to a phone number, an emergency address must be created and validated. Validation ensures that the emergency address is recognized and that it is in a correct format that can be used by emergency response services. Optionally, a location within the emergency address can be added to provide a more specific location for the user. For example, the emergency location could be a floor, wing, or office that is linked to a specific emergency address. Even though emergency address are validated, locations aren't.</span></span>
  
## <a name="what-are-emergency-addresses"></a><span data-ttu-id="8712d-110">緊急のアドレスとは</span><span class="sxs-lookup"><span data-stu-id="8712d-110">What are emergency addresses?</span></span>

<span data-ttu-id="8712d-p102">緊急アドレスがアクティブな電話番号に必要なことが必要な場合は、国/地域に依存します。米国で数値がユーザーに割り当てられているときに、緊急のアドレスが**必要**です。その他の国などでヨーロッパ、中東、アフリカ (EMEA)、緊急アドレスが**必要**ですから Office 365 を使用するか、別のサービス プロバイダーまたは carrier から転送、電話番号が表示された場合。</span><span class="sxs-lookup"><span data-stu-id="8712d-p102">An emergency address is required for active telephone numbers, but when it's required is dependent on the country/region. In the United States, an emergency address is **required** when a number is assigned to a user. For other countries, such as in Europe, the Middle East, and Africa (EMEA), an emergency address is **required** when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>
  
<span data-ttu-id="8712d-p103">緊急アドレスは、クールなアドレス、住所、または住所と呼びます可能性があります。組織のための適切な場所の住所またはクールなアドレスです。たとえば、 *12345 北メイン番地, Redmond, WA 98052*を適切なディスパッチ当局緊急の通話をルーティングして、緊急の発信者番号を検索するために使用されているアドレスです。ビジネスに 1 つ以上の実際の事業所がある場合は、緊急の 1 つ以上のアドレスを必要ことがあります。</span><span class="sxs-lookup"><span data-stu-id="8712d-p103">An emergency address may be referred to as a civic address, street address, or a physical address. It is the street or civic address of a place of business for your organization. For example, the address  *12345 North Main Street, Redmond, WA 98052*  is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller. It's likely that you will need more than one emergency address if your business has more than one physical business location.</span></span>
  
<span data-ttu-id="8712d-p104">緊急のアドレスを検証するには、正当なと緊急サービスの正しい形式であることを確認します。作成していない検証されると、緊急のアドレスを保存することが検証されたアドレスのみがユーザーに関連付けることができます。緊急のアドレスを検証して保存して後、ユーザーに割り当てることができます。保存した検証緊急のアドレスを変更する必要がある場合は、新しいアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8712d-p104">Validating an emergency address involves making sure that it is legitimate and correctly formatted for emergency response services. It's possible to create and save an emergency address that isn't validated, but only validated addresses can be associated to a user. Once an emergency address is validated and saved, it can be assigned to a user. If you need to change a saved validated emergency address, you will need to create a new one.</span></span>
  
## <a name="what-are-emergency-locations"></a><span data-ttu-id="8712d-122">緊急の場所とは</span><span class="sxs-lookup"><span data-stu-id="8712d-122">What are emergency locations?</span></span>

<span data-ttu-id="8712d-p105">緊急の場所では、緊急を文書内の正確なその他の場所を提供するアドレスに関連付けられます。緊急の場所を通常フロア、文書翼、またはオフィス番号、ユーザーが含まれています。任意の数と、緊急アドレスに関連付けられている場所のことができます。</span><span class="sxs-lookup"><span data-stu-id="8712d-p105">Emergency locations are associated with an emergency address to give a more exact location within a building. An emergency location is typically a floor, building wing, or office number where the user is located. You can have an unlimited number of locations associated with an emergency address.</span></span> 
  
<span data-ttu-id="8712d-p106">ユーザー緊急のアドレスを割り当てると、実際には、アドレスを割り当てるときに参照されている場所 ID です。場所の ID には、参照されている緊急アドレス (番地またはクールなアドレス) が含まれています。緊急の既定の場所は、文書内の場所が必要なときに大文字と小文字の緊急アドレスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="8712d-p106">When assigning a user an emergency address, it is actually a location ID that is referenced when you assign the address. The location ID includes the referenced emergency address (the street or civic address). A default emergency location is included with an emergency address for the case when in-building locations aren't needed.</span></span> 
  
## <a name="what-is-emergency-call-routing"></a><span data-ttu-id="8712d-129">緊急の通話のルーティングとよいですか。</span><span class="sxs-lookup"><span data-stu-id="8712d-129">What is emergency call routing?</span></span>

<span data-ttu-id="8712d-p107">緊急の最初の応答のディスパッチするとき、緊急アドレスや場所は、適切なディスパッチ センターにルーティング緊急の電話の処理中に使用されます。Skype for Business ユーザーは、緊急の番号をダイヤルするときは、国/地域によって異なりますサービスのパブリック安全性を解決するポイント (PSAP) に通話をルーティングする方法。米国、英国など、一部の国で呼び出しは、適切なディスパッチ センターに電話を接続する前に、ユーザーの現在の場所を決定する選別最初されます。その他の国/地域、通話は、緊急の発信者に関連付けられている電話番号を提供するディスパッチ センターに直接ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="8712d-p107">Emergency addresses and locations are used during the process of routing emergency calls to the appropriate dispatch center when dispatching emergency first responders. When a Skype for Business user dials an emergency number, how the call is routed to the serving Public Safety Answering Point (PSAP) will vary by country/region. In some countries, such as the United States and the United Kingdom, the calls will first be screened to determine the current location of the user before connecting the call to the appropriate dispatch center. In other countries/regions, calls will be routed directly to the dispatch center serving the phone number associated with the emergency caller.</span></span>
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a><span data-ttu-id="8712d-134">作成、追加、および緊急の場所とアドレスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="8712d-134">Creating, adding, and assigning emergency locations and addresses to your users</span></span>

1. <span data-ttu-id="8712d-p108">**緊急の場所を計画します。**最初には、緊急の場所を計画します。すべての自分の住所を一覧表示する必要があります。緊急のアドレスの場所が必要かどうかと、必要な場合に、次に、決定をに基づいては何か。たとえば、ビジネスに 3 office 建物ごとに 4 フロアがある場合は、フロア 1 ~ 4 をそれぞれの保存場所として表示されると、3 つの緊急のアドレスを指定する必要があることそうなします。</span><span class="sxs-lookup"><span data-stu-id="8712d-p108">**Plan for emergency locations** The first step is to plan for your emergency locations. You need to list all of your physical addresses. Then, based on that, determine whether locations for the emergency addresses are needed and if so, what they are. For example, if a business has 3 office buildings each with 4 floors, it is likely that there need to be 3 emergency addresses, with floors 1-4 listed as a location for each.</span></span>
    
2. <span data-ttu-id="8712d-p109">**を作成して、緊急の場所を検証**次の手順を作成して、緊急の住所を確認します。緊急アドレスを作成するときに、検証することができます。緊急のアドレスを作成するには、[追加または削除するが、組織のアドレスに緊急](add-or-remove-an-emergency-address-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8712d-p109">**Create and validate your emergency locations** The next step is to create and validate your emergency addresses. When you create an emergency address, you can validate it. To create an emergency address, see [Add or remove an emergency address for your organization](add-or-remove-an-emergency-address-for-your-organization.md).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8712d-p110">番地またはクールなアドレスを検証するには、正当なし、正しい形式であることを確認します。パスの入力規則も、市区町村の入力ミスの名前など、部分的に正しい緊急のアドレス番号が渡すことができます。検証プロセスでは、適切な緊急ディスパッチ センターに通話をルーティングするのにには、十分な情報が含まれているかどうかは、指定されたアドレスのすべての項目を使用します。したがって、検証で返されに電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8712d-p110">Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as a mistyped name of the city, may pass still pass validation. The validation process uses all parts of a given address to determine if it contains enough information to route the call to the appropriate emergency dispatch center. If so, it will be returned as validated and then can be assigned to a phone number.</span></span> 
  
3. <span data-ttu-id="8712d-p111">**電話番号を取得します。**次の手順では、ユーザーの電話番号を取得します。これは、「移植」、または Office 365 で、既存の電話番号に転送する、Office 365 から新しい電話番号を取得することによって行うことができます。手順の実行を表示するには、 [Office 365 への電話番号に転送](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8712d-p111">**Get phone numbers** The next step is to get phone numbers for your users. You can do this by getting new phone numbers from Office 365 or by "porting" or transferring your existing phone numbers over to Office 365. To see the complete steps, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
    
4. <span data-ttu-id="8712d-p112">**電話番号を割り当てる**最後の手順では、ユーザーが携帯電話の発信や受信を有効にします。これを行うには、各ユーザーに電話番号を割り当てる必要があります。[割り当て、変更、またはユーザーの電話番号を削除する](assign-change-or-remove-a-phone-number-for-a-user.md)電話番号を割り当てるを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8712d-p112">**Assign phone numbers** The last step is to enable users to make and receive phone calls. To do this, you must assign a phone number to each user. See [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md) to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="8712d-152">これよりも、その他の電話番号を取得する必要がある場合は、[ビジネス製品 - 管理者向けヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="8712d-152">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="8712d-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8712d-153">Related topics</span></span>
[<span data-ttu-id="8712d-154">アドレスの入力規則とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="8712d-154">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="8712d-155">さまざまなプランの呼び出し用の電話番号</span><span class="sxs-lookup"><span data-stu-id="8712d-155">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="8712d-156">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="8712d-156">Emergency calling terms and conditions</span></span>](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="8712d-157">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="8712d-157">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
