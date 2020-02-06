---
title: Skype for Business Server のコアインフラストラクチャのベストプラクティス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。 この方法は、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体でもメリットがあります。 これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に、この手順を実行することをお勧めします。
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815685"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="0ae23-105">Skype for Business Server のコアインフラストラクチャのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="0ae23-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="0ae23-106">システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。</span><span class="sxs-lookup"><span data-stu-id="0ae23-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="0ae23-107">この方法は、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体でもメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="0ae23-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="0ae23-108">これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に、この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ae23-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="0ae23-109">ダウンタイムが発生する可能性のある偶発的または明確の危害から Skype for Business Server 展開のサーバーを保護するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ae23-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="0ae23-110">各サーバーに、常に最新のセキュリティ更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="0ae23-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="0ae23-111">マイクロソフト テクニカル セキュリティ情報通知を購読すると、マイクロソフト製品に関するセキュリティ速報を受信できます。</span><span class="sxs-lookup"><span data-stu-id="0ae23-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="0ae23-112">登録するには、 [Microsoft テクニカルセキュリティ通知の web サイト](https://go.microsoft.com/fwlink/p/?LinkId=145202)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="0ae23-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="0ae23-113">アクセス権が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ae23-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="0ae23-p104">物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="0ae23-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="0ae23-118">Skype for Business Server をインストールするコンピューターには必要ない Windows Server オペレーティングシステムサービスを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ae23-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="0ae23-119">サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。</span><span class="sxs-lookup"><span data-stu-id="0ae23-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="0ae23-120">サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="0ae23-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="0ae23-121">DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ae23-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

