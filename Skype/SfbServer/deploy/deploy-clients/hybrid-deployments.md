---
title: Skype Room System のハイブリッド展開
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: このトピックでは、ハイブリッド環境で Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219677"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Room System のハイブリッド展開

このトピックでは、ハイブリッド環境で Skype Room System を展開する方法について説明します。
  
## <a name="hybrid-deployments"></a>ハイブリッド展開

ご使用のトポロジで Skype for Business Server と Exchange Online があり、Exchange Online で Skype Room System リソースメールボックスをホストする場合は、次の手順を実行します。 このセクションでは、Exchange Online と Exchange Server の両方が展開されているハイブリッドシナリオについても説明します。
  
説明のために、LyncSample.com をオンプレミスのドメインに使用し、LyncSample.ccstp.net をオンラインドメインに使用します。
  
1. 「Exchange Online のプロビジョニング」で説明されているように、Exchange Online 管理シェルに接続して、Exchange 管理センター (LyncSample.ccsctp.net) でリソースメールボックスを作成します。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Lrstest5@LyncSample.ccsctp.net を使用してログインするには、OWA 接続を確認します。
    
2. Microsoft 365 または Office 365 Exchange 管理センターで、電子メールアドレス lrstest5@LyncSample.com (オンプレミスドメイン) を追加して、それを返信アドレスとして設定します。
    
3. オンプレミスの Active Directory ユーザー lrstest5@LyncSample.com を作成し、電子メールアドレスを lrstest5@LyncSample.com に設定し、ターゲットアドレスを lrstest5@LyncSample.com に設定します。
    
4. ディレクトリ同期をトリガーし、同期が完了した後、ユーザーが AAD で合併し、Microsoft 365 または Office 365 Exchange 管理センターで受信者のリソースのプロパティを変更できないことを確認します。
    
5. Lrstest5@LyncSample.com を使用して OWA 接続を確認します。 (以前は、オンラインドメインを使用して OWA 接続を確認しています)。
    
    メールボックスを作成した後、Exchange Online 管理シェルで [CalendarProcessing] を使用して、メールボックスを構成することができます。 詳細については、「単一フォレストのオンプレミス展開」の手順 3 ~ 6 を参照してください。
    
   > [!NOTE]
   > Exchange Server と Exchange Online を使用したハイブリッド環境の場合は、Exchange 管理シェルに移動し、-Remotemlrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room を有効にします。 ディレクトリ同期をトリガーします。 
  
    Exchange Online で Skype Room System メールボックスをホストする場合は、これらの Exchange 管理シェルの手順は必要ありません。また、手順6に進むことができます。
    
6. Skype for Business 管理シェルで次のコマンドレットを実行して、skype for business の Skype Room System アカウントを有効にします。
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 上記のシナリオで Skype for business Server ではなく、Skype for business Online を使用している場合は、Exchange リソースメールボックスのプロビジョニング後に、「Skype for business Online のプロビジョニング」で説明されているように、Skype for Business アカウントをプロビジョニングします。 
  

