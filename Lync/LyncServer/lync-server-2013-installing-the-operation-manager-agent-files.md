---
title: 'Lync Server 2013: Operation Manager エージェントファイルのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e685abf7916c446bf9acf73e50f5633271b2942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="4f333-102">Lync Server 2013 での Operation Manager エージェントファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="4f333-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f333-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4f333-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4f333-104">Operations Manager エージェントファイルをコンピューターにインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4f333-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="4f333-105">System Center セットアップメディアで、 **setupom.exe**をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="4f333-106">System Center Operation Manager セットアップで、[ **Operations Manager エージェントのインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="4f333-107">System Center Setup ウィザードの [ **System Center Operations Manager セットアップウィザードへようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="4f333-108">[インストール**先フォルダー** ] ページで、Operations Manager エージェントファイルをインストールするフォルダーを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="4f333-109">[**管理グループの構成**] ページで、[**管理グループ情報の指定**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="4f333-110">[管理**グループの構成**] ページで、[管理**グループ名**] ボックスに operations manager 管理グループの名前を入力し、[**管理サーバー** ] ボックスに、operations manager サーバーのホスト名 (たとえば、「atl-scom-001」) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f333-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="4f333-111">Operations Manager で使用されるポート番号を変更した場合は、[管理サーバーのポート] ボックスに新しいポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f333-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="4f333-112">それ以外の場合は、ポートを既定値の5723のままにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="4f333-113">[**エージェントアクションアカウント**] ページで、[**ローカルシステム**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="4f333-114">[ **Microsoft update** ] ページで、[ **microsoft update を使用しない**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="4f333-115">[**インストールの準備完了**] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="4f333-116">[ **System Center Operations Manager セットアップウィザードを完了**しています] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="4f333-117">**[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f333-117">Click **Exit**.</span></span>

<span data-ttu-id="4f333-118">System Center 2007 R2 を使用している場合は、[**スタート**]、[**すべてのプログラム**]、[ **System Center Operations manager 2007 R2**]、[ **operations manager シェル**] の順にクリックして、エージェントが作成されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4f333-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="4f333-119">Operations Manager シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4f333-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="4f333-120">すべての Operations Manager エージェントの一覧が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f333-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="4f333-121">System Center 2012 を使用している場合は、Operations 2012 Manager シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f333-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

