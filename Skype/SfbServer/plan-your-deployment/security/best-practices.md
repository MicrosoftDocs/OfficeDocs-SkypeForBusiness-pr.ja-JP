---
title: Skype for Business Server のコア インフラストラクチャのベスト プラクティス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 一般に、システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段を既に講じていることでしょう。 これらのプラクティスは、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体にもメリットがあります。 これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に実装することをお勧めします。
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832247"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="92047-105">Skype for Business Server のコア インフラストラクチャのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="92047-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="92047-106">一般に、システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段を既に講じていることでしょう。</span><span class="sxs-lookup"><span data-stu-id="92047-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="92047-107">これらのプラクティスは、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体にもメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="92047-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="92047-108">これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92047-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="92047-109">Skype for Business Server 展開内のサーバーを、ダウンタイムの原因になる偶発的または目的上の損害から保護するには、次の予防措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="92047-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="92047-110">各サーバーに、常に最新のセキュリティ更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="92047-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="92047-111">マイクロソフト テクニカル セキュリティ情報通知サービスに登録すると、マイクロソフト製品に関するセキュリティ速報を受信できます。</span><span class="sxs-lookup"><span data-stu-id="92047-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="92047-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="92047-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="92047-113">アクセス権が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92047-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="92047-p104">物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="92047-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="92047-118">Skype for Business Server をインストールするコンピューターで不要な Windows Server オペレーティング システム サービスを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92047-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="92047-119">サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。</span><span class="sxs-lookup"><span data-stu-id="92047-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="92047-120">サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="92047-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="92047-121">DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92047-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

