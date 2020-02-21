---
title: 'Lync Server 2013: スマートカード認証用にエンタープライズ CA を構成する'
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
ms.openlocfilehash: 41f6f2fdbf30696941e97d08cd1daf2e793f63ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="74e5a-102">Lync Server 2013 でのスマートカード認証のエンタープライズ CA の構成</span><span class="sxs-lookup"><span data-stu-id="74e5a-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74e5a-103">_**トピックの最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="74e5a-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="74e5a-104">次のセクションでは、スマートカード認証をサポートするようにエンタープライズのルート証明機関 (CA) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="74e5a-105">エンタープライズルート CA のインストール方法については、「エンタープライズのルート証明機関をインストール[https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e5a-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="74e5a-106">スマートカード認証をサポートするようにエンタープライズルート証明機関を構成する</span><span class="sxs-lookup"><span data-stu-id="74e5a-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="74e5a-107">次の手順では、スマートカード認証をサポートするようにエンタープライズルート CA を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="74e5a-108">ドメイン管理者アカウントを使用して、エンタープライズ CA コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="74e5a-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="74e5a-109">システムマネージャーを起動し、証明機関 Web 登録役割がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="74e5a-110">[**管理ツール**] メニューから、**証明機関**管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="74e5a-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="74e5a-111">ナビゲーションウィンドウで、[**証明機関**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="74e5a-112">[**証明書テンプレート**] を右クリックし、[**新規作成**] を選択して、[**発行する証明書テンプレート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="74e5a-113">[**登録エージェント**]、[**スマートカードユーザー**]、および [**スマートカードログオン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="74e5a-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74e5a-114">Click **OK**.</span></span>

8.  <span data-ttu-id="74e5a-115">[**証明書テンプレート**] を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="74e5a-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="74e5a-116">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-116">Select **Manage**.</span></span>

10. <span data-ttu-id="74e5a-117">スマートカードユーザーテンプレートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="74e5a-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="74e5a-118">[**セキュリティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="74e5a-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="74e5a-119">アクセス許可を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="74e5a-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="74e5a-120">読み取り/登録 (許可) のアクセス許可を持つ個々のユーザー AD アカウントを追加するか、または</span><span class="sxs-lookup"><span data-stu-id="74e5a-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="74e5a-121">読み取り/登録 (許可) のアクセス許可を持つスマートカードユーザーを含むセキュリティグループを追加するか、または</span><span class="sxs-lookup"><span data-stu-id="74e5a-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="74e5a-122">読み取り/登録 (許可) のアクセス許可を持つドメインユーザーグループを追加する</span><span class="sxs-lookup"><span data-stu-id="74e5a-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

