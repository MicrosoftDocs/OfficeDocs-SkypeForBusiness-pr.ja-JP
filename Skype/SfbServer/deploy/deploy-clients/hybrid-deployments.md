---
title: Skype Room System のハイブリッド展開
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: このトピックでは、ハイブリッド環境に Skype Room System を展開する方法について説明します。
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805897"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Room System のハイブリッド展開

このトピックでは、ハイブリッド環境に Skype Room System を展開する方法について説明します。
  
## <a name="hybrid-deployments"></a>ハイブリッド展開

トポロジに Skype for Business Server と Exchange Online が含まれますが、Exchange Online で Skype Room System リソース メールボックスをホストする場合は、次の手順を実行します。 このセクションでは、Exchange Online と Exchange Online の両方を展開するハイブリッド Exchange Serverします。
  
説明を目的として、オンプレミス ドメインLyncSample.com、オンライン ドメインのLyncSample.ccstp.netを使用します。
  
1. 「Exchange Online プロビジョニング」の説明に従って Exchange Online 管理シェルに接続して、Exchange 管理センター (LyncSample.ccsctp.net) でリソース メールボックスを作成します。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    OWA 接続を確認するには、lrstest5@LyncSample.ccsctp.netを使用します。
    
2. Microsoft 365 または Office 365 Exchange 管理センターで、電子メール アドレス lrstest5@LyncSample.com (オンプレム ドメイン) を追加し、返信アドレスとして設定します。
    
3. 事前に Active Directory ユーザー アカウントを作成lrstest5@LyncSample.com電子メール アドレスを lrstest5@LyncSample.com に設定し、ターゲット アドレスを lrstest5@LyncSample.com。
    
4. ディレクトリ同期をトリガーし、同期が完了したら、ユーザーが AAD にマージされ、Microsoft 365 または Office 365 Exchange 管理センターで受信者のリソースのプロパティを変更できない点を確認します。
    
5. 次のコマンドを使用して OWA 接続lrstest5@LyncSample.com。 (以前は、オンライン ドメインを使用して OWA 接続を確認しました。)
    
    メールボックスを作成した後、Exchange Online 管理シェルSet-CalendarProcessingを使用してメールボックスを構成できます。 詳細については、「Single Forest On-prem Deployments」の手順 3 . ~ 6. を参照してください。
    
   > [!NOTE]
   > Exchange Server と Exchange Online を使用するハイブリッド環境がある場合は、Exchange 管理シェルに移動し、-RemoteRoutingAddress Enable-RemoteMailbox lrstest5@LyncSample.com -Room lrstest5@LyncSample.mail.ccsctp.netに移動します。 その後、ディレクトリ同期をトリガーします。 
  
    Exchange Online で Skype Room System メールボックスをホストする場合、これらの Exchange 管理シェルの手順は必要ありません。手順 6 に進みます。
    
6. Skype for Business 管理シェルで次のコマンドレットを実行して、Skype for Business の Skype Room System アカウントを有効にする。
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 上記のシナリオで Skype for Business Server ではなく Skype for Business Online を使用している場合は、Exchange リソース メールボックスのプロビジョニング後に、Skype for Business Online プロビジョニングの説明に従って Skype for Business アカウントをプロビジョニングします。 
  

