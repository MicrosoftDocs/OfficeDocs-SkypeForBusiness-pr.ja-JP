---
title: Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '[外部設定] のプロパティを定義するには、次のように構成します。'
ms.openlocfilehash: 6b833e89a8e1288af9a203dd5f44201c253ff2f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282599"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a><span data-ttu-id="49b46-103">Lync Server 2010 用のエッジ サーバー FQDN 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="49b46-103">Edge Server FQDN Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="49b46-104">[**外部設定**] のプロパティを定義するには、次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="49b46-104">To define the properties under **External settings**, configure the following:</span></span>
  
<span data-ttu-id="49b46-105">Web 会議や音声/ビデオ用のプールの FQDN と IP アドレスを個別に定義する場合は、[ **web 会議と ip アドレスを別々に使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="49b46-105">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to define distinct Pool FQDN and IP addresses for web conferencing and audio/video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="49b46-106">独立した FQDN と IP アドレスのチェックボックスをオンにしない場合は、エッジサーバーによって提供される3つのサービスごとに個別のポートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b46-106">If you choose to not select the check box for separate FQDN and IP addresses, you must provide distinct ports for each of the three services provided by the Edge Server.</span></span> <span data-ttu-id="49b46-107">構成する完全修飾ドメイン名は、アクセスエッジサービスに関連付けられている FQDN です。</span><span class="sxs-lookup"><span data-stu-id="49b46-107">The only fully qualified domain name that is to configure is the FQDN associated with the Access Edge service.</span></span> 
  
<span data-ttu-id="49b46-108">A/v Edge サービスでネットワークアドレス変換 (NAT) IP アドレスと構成を使用する場合は、[ **a/v edge サービスは nat を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="49b46-108">Select the **A/V Edge service is NAT enabled** check box if you want the A/V Edge service to use a network address translation (NAT) IP address and configuration.</span></span>
  
<span data-ttu-id="49b46-109">有効なエッジサービスの場合、[**ポート**] に**プールの FQDN**とポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="49b46-109">For the enabled Edge services, you type a **Pool FQDN** and a port under **Ports**</span></span>
  
- <span data-ttu-id="49b46-110">**アクセスエッジサービス**プールの FQDN と、サービスを一意に識別するポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="49b46-110">Define the **Access Edge service** Pool FQDN and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="49b46-111">**Web 会議エッジサービス**プールの FQDN を定義します ([web 会議用に個別の FQDN と IP アドレスを有効にし、A/V が選択されていない場合)。また、サービスを一意に識別するポート。</span><span class="sxs-lookup"><span data-stu-id="49b46-111">Define the **Web Conferencing Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
- <span data-ttu-id="49b46-112">**A/v Edge サービス**プールの FQDN を定義します ([web 会議のために別々の FQDN と IP アドレスを有効にし、a/v が選択されていない場合)。また、サービスを一意に識別するポート。</span><span class="sxs-lookup"><span data-stu-id="49b46-112">Define the **A/V Edge service** Pool FQDN (If Enable separate FQDN and IP address for web conferencing and A/V is not selected) and a port that uniquely identifies the service.</span></span>
    
  <span data-ttu-id="49b46-113">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="49b46-113">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="49b46-114">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="49b46-114">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="49b46-115">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="49b46-115">**Help** Displays this help screen.</span></span>
  

