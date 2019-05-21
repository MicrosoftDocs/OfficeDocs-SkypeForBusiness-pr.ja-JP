---
title: 証明書ウィザード
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: 証明書の [要求]、[割り当て]、[削除]、または [表示] を行うには、証明書ウィザードを使用します。 この場合は、RTCUniversalServerAdmins グループのメンバーとしてログインする必要があります。 パブリック証明機関 (CA) からの証明書を要求する場合に、別のグループ メンバーシップは不要です。 組織の公開キー基盤 (PKI) に対して証明書を要求するには、必要なグループメンバーシップについて確認する必要があります。 要求タスクでは、PKI の発行 CA から証明書を要求するために使用される代替資格情報を入力できます。
ms.openlocfilehash: daafbdd6730b86b7509323528405bec5277d264d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298962"
---
# <a name="certificate-wizard"></a><span data-ttu-id="5ff66-107">証明書ウィザード</span><span class="sxs-lookup"><span data-stu-id="5ff66-107">Certificate Wizard</span></span>
 
<span data-ttu-id="5ff66-108">証明書の [**要求**]、[**割り当て**]、[**削除**]、または [**表示**] を行うには、証明書ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ff66-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="5ff66-109">この場合は、RTCUniversalServerAdmins グループのメンバーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff66-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="5ff66-110">パブリック証明機関 (CA) からの証明書を要求する場合に、別のグループ メンバーシップは不要です。</span><span class="sxs-lookup"><span data-stu-id="5ff66-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="5ff66-111">組織の公開キー基盤 (PKI) に対して証明書を要求するには、必要なグループメンバーシップについて確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff66-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="5ff66-112">要求タスクでは、PKI の発行 CA から証明書を要求するために使用される代替資格情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="5ff66-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="5ff66-113">新しい証明書を要求するには、[**要求**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="5ff66-114">まだ割り当てられていない証明書を割り当てるには、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="5ff66-115">以前に割り当てた証明書を削除するには、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ff66-p103">[**削除**] ボタンは、証明書が以前に割り当てられている場合にのみ使用可能になります。[**削除**] ボタンが使用不可 (灰色表示) の場合、割り当てられた証明書はありません。</span><span class="sxs-lookup"><span data-stu-id="5ff66-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="5ff66-118">割り当てられた証明書を表示するには、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ff66-p104">[**表示**] ボタンは、証明書が以前に割り当てられている場合にのみ使用可能になります。[**表示**] ボタンが灰色表示の場合、割り当てられた証明書はありません。</span><span class="sxs-lookup"><span data-stu-id="5ff66-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="5ff66-121">現在の証明書割り当て画面を更新するには、[**最新の情報に更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="5ff66-122">証明書ストアに存在しない証明書をインポートするには、[**証明書のインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ff66-123">[**証明書のインポート**] は、通常、証明書ウィザードからの要求以外のプロセスによって受信した証明書を処理するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="5ff66-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="5ff66-124">たとえば、PKI 管理者が証明書を作成し、ユーザーが使用できるようにするとします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="5ff66-125">[**証明書のインポート**] を使用して、証明書をコンピューターの証明書ストアにインポートし、Skype For business Server で利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5ff66-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="5ff66-p106">CA 管理者の承認を必要とする、組織の CA からの証明書要求の要求処理を完了するには、[**保留中の証明書の処理**] をクリックします。証明書要求により、状態が保留中として戻され、保留要求の ID 番号も表示されます。保留状態の証明書の処理を続行するには、[**最新の情報に更新**] をクリックして [**保留中の証明書の処理**] ボタンを有効にします。[**保留中の証明書の処理**] ボタンが灰色表示ではなくなります。その後、保留要求の取得を試みることができますが、証明書が CA 管理者によって発行または拒否されるまで、要求の状態は保留のままになります。証明書ウィザードによって作成された有効な保留中の要求が存在しない場合、ボタンは操作可能になりません。</span><span class="sxs-lookup"><span data-stu-id="5ff66-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

