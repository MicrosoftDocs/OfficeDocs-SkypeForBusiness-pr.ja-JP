---
title: Skype Room System のハイブリッド展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: このトピックでは、ハイブリッド環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 016a4cf379200dc87b8f94d13a65f10f6c3af25f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234431"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Room System のハイブリッド展開

このトピックでは、ハイブリッド環境で Skype Room System を展開する方法について説明します。
  
## <a name="hybrid-deployments"></a>ハイブリッド展開

トポロジで Skype for Business Server と Exchange Online を使用していて、Exchange Online で Skype Room System リソースメールボックスをホストする場合は、次の手順を実行します。 またこのセクションでは、Exchange Online と Exchange Server の両方が展開されているハイブリッドのシナリオについて説明します。
  
ここでは、LyncSample.com を使って、オンプレミスのドメインとオンラインドメインの LyncSample.ccstp.net を使用しています。
  
1. 「Exchange Online のプロビジョニング」で説明されているように、exchange Online Management shell に接続して、exchange 管理センター (LyncSample.ccsctp.net) でリソースメールボックスを作成します。
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Lrstest5@LyncSample.ccsctp.net を使用してログインするには、OWA の接続を確認することができます。
    
2. Office 365 Exchange 管理センターで、メールアドレス lrstest5@LyncSample.com (オンプレミスドメイン) を追加して、それを返信アドレスとして設定します。
    
3. オンプレミスの Active Directory ユーザー lrstest5@LyncSample.com を作成し、メールアドレスを lrstest5@LyncSample.com に設定して、ターゲットアドレスを lrstest5@LyncSample.com に設定します。
    
4. 同期が完了した後、同期が完了したら、ユーザーが AAD に統合されたことを確認し、Office365 Exchange 管理センターで受信者のリソースのプロパティを変更できないことを確認します。
    
5. Lrstest5@LyncSample.com を使用して OWA 接続を確認します。 (以前は、オンラインドメインを使用して OWA 接続を確認していること)。
    
    メールボックスを作成した後、Exchange Online 管理シェルで Set-CalendarProcessing を使用してメールボックスを構成できます。詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。
    
   > [!NOTE]
   > Exchange Server と Exchange Online のハイブリッド環境を使用している場合は、Exchange 管理シェルに移動して、[Box lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net] を有効にします。 次に、ディレクトリ同期をトリガーします。 
  
    Exchange Online で Skype Room システムメールボックスをホストする場合、これらの Exchange 管理シェルの手順は必要ありません。手順6に進むことができます。
    
6. Skype for business の管理シェルで次のコマンドレットを実行して、skype for Business の Skype Room System アカウントを有効にします。
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 上記のシナリオで Skype for Business Server の代わりに Skype for business Online を使用している場合は、Exchange リソースメールボックスをプロビジョニングした後、「Skype for Business Online のプロビジョニング」で説明されているように、Skype for Business アカウントをプロビジョニングします。 
  

