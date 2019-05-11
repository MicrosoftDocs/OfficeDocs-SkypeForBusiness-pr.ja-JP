---
title: Skype ビジネス サーバー用のコア ・ インフラストラクチャに関するベスト プラクティス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。 これらのプラクティスは、ビジネスのサーバー インフラストラクチャのため、Skype だけでなく、ネットワーク全体を活用できます。 これらのプラクティスを実装していない場合は、設定するように Skype をビジネス サーバーを展開する前にすることをお勧めします。
ms.openlocfilehash: 66725331c84e3f2d24e496489e0db8ef9866d0e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896355"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="2b004-105">Skype ビジネス サーバー用のコア ・ インフラストラクチャに関するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="2b004-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="2b004-106">システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。</span><span class="sxs-lookup"><span data-stu-id="2b004-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="2b004-107">これらのプラクティスは、ビジネスのサーバー インフラストラクチャのため、Skype だけでなく、ネットワーク全体を活用できます。</span><span class="sxs-lookup"><span data-stu-id="2b004-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="2b004-108">これらのプラクティスを実装していない場合は、設定するように Skype をビジネス サーバーを展開する前にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b004-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="2b004-109">ダウンタイムが発生する可能性がある事故または故意による被害から、Skype をビジネス サーバーの展開内のサーバーを保護するためには、次の対策を講じる。</span><span class="sxs-lookup"><span data-stu-id="2b004-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="2b004-110">各サーバーに、常に最新のセキュリティ更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="2b004-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="2b004-111">マイクロソフト テクニカル セキュリティ情報通知を購読すると、マイクロソフト製品に関するセキュリティ速報を受信できます。</span><span class="sxs-lookup"><span data-stu-id="2b004-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="2b004-112">ニュースレターを購読するには、[技術的なセキュリティ通知を Microsoft の web サイト](https://go.microsoft.com/fwlink/p/?LinkId=145202)に移動します。</span><span class="sxs-lookup"><span data-stu-id="2b004-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="2b004-113">アクセス権が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b004-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="2b004-p104">物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="2b004-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="2b004-118">ビジネス サーバーの Skype をインストールしたコンピューターで不要な Windows サーバー オペレーティング システムのサービスを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b004-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="2b004-119">サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。</span><span class="sxs-lookup"><span data-stu-id="2b004-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="2b004-120">サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="2b004-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="2b004-121">DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b004-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

