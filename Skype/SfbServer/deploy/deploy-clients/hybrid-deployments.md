---
title: SkypeRoom System ハイブリッド展開
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: ハイブリッド環境にルーム システムをSkypeする方法については、このトピックを参照してください。
ms.openlocfilehash: caebf77f0ef5abb2b56c64446ad04a052d8f98f9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841949"
---
# <a name="skype-room-system-hybrid-deployments"></a>SkypeRoom System ハイブリッド展開

ハイブリッド環境にルーム システムをSkypeする方法については、このトピックを参照してください。
  
## <a name="hybrid-deployments"></a>ハイブリッド展開

トポロジにサーバーとサーバーがSkype for Business Serverし、Exchange Online上で Skype Room System リソース メールボックスをホストする場合は、次の手順に従Exchange Online。 このセクションでは、ハイブリッド シナリオについて説明します。このシナリオでは、Exchange OnlineとExchange Serverします。
  
例を示す目的で、LyncSample.com ドメインとオンライン ドメインの LyncSample.ccstp.net を使用します。
  
1. 「プロビジョニング」のExchangeに示 LyncSample.ccsctp.net 管理シェルに接続して、Exchange Online 管理センター (LyncSample.ccsctp.net Exchange Online) にリソース メールボックスを作成します。
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    OWA 接続を確認するには、lrstest5@LyncSample.ccsctp.net を使用します。
    
2. 管理センター Microsoft 365または Office 365 Exchangeで、電子メール アドレス lrstest5@LyncSample.com (on-prem ドメイン) を追加し、返信アドレスとして設定します。
    
3. On-prem Active Directory ユーザー lrstest5@LyncSample.com を作成し、電子メール アドレスを lrstest5@LyncSample.com に設定し、ターゲット アドレスを lrstest5@LyncSample.com。
    
4. ディレクトリ同期をトリガーし、同期が完了したら、ユーザーが AAD にマージされ、Microsoft 365 または Office 365 Exchange 管理センターの受信者のリソースのプロパティを変更できないか確認します。
    
5. デバイスを使用して OWA 接続を lrstest5@LyncSample.com。 (以前は、オンライン ドメインを使用して OWA 接続を確認しました。
    
    メールボックスを作成した後、管理シェルSet-CalendarProcessingのExchange Onlineを使用してメールボックスを構成できます。 詳細については、「Single Forest On-prem Deployments」の「手順 3 ~ 6」を参照してください。
    
   > [!NOTE]
   > Exchange Server と Exchange Online のハイブリッド環境がある場合は、Exchange 管理シェルと Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room に移動します。 次に、ディレクトリ同期をトリガーします。 
  
    Exchange Online で Skype Room System メールボックスをホストする場合、これらの Exchange 管理シェルの手順は必要ありません。手順 6 に進みます。
    
6. 管理シェルでSkypeコマンドレットを実行して、Skype for Businessのルーム システム アカウントを有効Skype for Businessします。
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 上記のシナリオで Skype for Business Server の代わりに Skype for Business Online を使用している場合は、Exchange リソース メールボックスをプロビジョニングした後、Skype for Business アカウントを準備します (Skype for Businessオンライン プロビジョニング。 
  

