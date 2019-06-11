---
title: 'Lync Server 2013: スマートカード認証用のエンタープライズ CA の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="0e91f-102">Lync Server 2013 でのスマートカード認証用のエンタープライズ CA の構成</span><span class="sxs-lookup"><span data-stu-id="0e91f-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e91f-103">_**最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="0e91f-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="0e91f-104">以下のセクションでは、スマートカード認証をサポートするようにエンタープライズのルート証明機関 (CA) を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="0e91f-105">エンタープライズルート CA をインストールする方法については、「エンタープライズルート証明機関をインストール[http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e91f-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="0e91f-106">スマートカード認証をサポートするようにエンタープライズルート証明機関を構成する</span><span class="sxs-lookup"><span data-stu-id="0e91f-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="0e91f-107">スマート カード認証をサポートするようにエンタープライズ ルート CA を構成する方法を以下の手順で説明します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="0e91f-108">ドメイン管理者のアカウントを使用してエンタープライズ CA コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="0e91f-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="0e91f-109">システム マネージャーを起動し、証明機関 Web 登録の役割がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="0e91f-110">[**管理ツール**] メニューから**証明機関**管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e91f-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="0e91f-111">ナビゲーション ウィンドウで、[**証明機関**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="0e91f-112">[**証明書テンプレート**] を右クリックし、[**新規作成**] をクリックして、[**発行する証明書テンプレート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="0e91f-113">[**登録エージェント**]、[**スマート カード ユーザー**]、[**スマート カード ログオン**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e91f-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="0e91f-114">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e91f-114">Click **OK**.</span></span>

8.  <span data-ttu-id="0e91f-115">[**証明書テンプレート**] を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0e91f-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="0e91f-116">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-116">Select **Manage**.</span></span>

10. <span data-ttu-id="0e91f-117">スマート カード ユーザー テンプレートのプロパティを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e91f-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="0e91f-118">[**セキュリティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e91f-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="0e91f-119">アクセス許可を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="0e91f-120">読み取り/登録 (許可) アクセス許可を指定して個別のユーザー AD アカウントを追加します。または</span><span class="sxs-lookup"><span data-stu-id="0e91f-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="0e91f-121">読み取り/登録 (許可) のアクセス許可を指定してスマート カード ユーザーを含むセキュリティ グループを追加します。または</span><span class="sxs-lookup"><span data-stu-id="0e91f-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="0e91f-122">読み取り/登録 (許可) のアクセス許可を指定してドメイン ユーザー グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="0e91f-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

