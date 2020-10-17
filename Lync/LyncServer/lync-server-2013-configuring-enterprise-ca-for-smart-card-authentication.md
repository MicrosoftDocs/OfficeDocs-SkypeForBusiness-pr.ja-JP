---
title: 'Lync Server 2013: スマートカード認証用にエンタープライズ CA を構成する'
description: 'Lync Server 2013: スマートカード認証用にエンタープライズ CA を構成する。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98044c96dd04d02fd87609918f309cf65227b133
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548443"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="4c78a-103">Lync Server 2013 でのスマートカード認証のエンタープライズ CA の構成</span><span class="sxs-lookup"><span data-stu-id="4c78a-103">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c78a-104">_**トピックの最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="4c78a-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="4c78a-105">次のセクションでは、スマートカード認証をサポートするようにエンタープライズのルート証明機関 (CA) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-105">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="4c78a-106">エンタープライズルート CA のインストール方法については、「エンタープライズのルート証明機関をインストールする」を参照してください [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) 。</span><span class="sxs-lookup"><span data-stu-id="4c78a-106">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="4c78a-107">スマートカード認証をサポートするようにエンタープライズルート証明機関を構成する</span><span class="sxs-lookup"><span data-stu-id="4c78a-107">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="4c78a-108">次の手順では、スマートカード認証をサポートするようにエンタープライズルート CA を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-108">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="4c78a-109">ドメイン管理者アカウントを使用して、エンタープライズ CA コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="4c78a-109">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="4c78a-110">システムマネージャーを起動し、証明機関 Web 登録役割がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-110">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="4c78a-111">[ **管理ツール** ] メニューから、 **証明機関** 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="4c78a-111">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="4c78a-112">ナビゲーションウィンドウで、[ **証明機関**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-112">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="4c78a-113">[ **証明書テンプレート**] を右クリックし、[ **新規作成**] を選択して、[ **発行する証明書テンプレート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-113">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="4c78a-114">[ **登録エージェント**]、[ **スマートカードユーザー**]、および [ **スマートカードログオン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-114">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="4c78a-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c78a-115">Click **OK**.</span></span>

8.  <span data-ttu-id="4c78a-116">[ **証明書テンプレート**] を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4c78a-116">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="4c78a-117">[ **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-117">Select **Manage**.</span></span>

10. <span data-ttu-id="4c78a-118">スマートカードユーザーテンプレートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="4c78a-118">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="4c78a-119">[ **セキュリティ** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c78a-119">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="4c78a-120">アクセス許可を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="4c78a-120">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="4c78a-121">読み取り/登録 (許可) のアクセス許可を持つ個々のユーザー AD アカウントを追加するか、または</span><span class="sxs-lookup"><span data-stu-id="4c78a-121">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="4c78a-122">読み取り/登録 (許可) のアクセス許可を持つスマートカードユーザーを含むセキュリティグループを追加するか、または</span><span class="sxs-lookup"><span data-stu-id="4c78a-122">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="4c78a-123">読み取り/登録 (許可) のアクセス許可を持つドメインユーザーグループを追加する</span><span class="sxs-lookup"><span data-stu-id="4c78a-123">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

