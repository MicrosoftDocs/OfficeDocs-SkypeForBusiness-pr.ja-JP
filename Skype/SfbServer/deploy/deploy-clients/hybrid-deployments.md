---
title: Skype Room System のハイブリッド展開
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: ハイブリッド環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Room System のハイブリッド展開
 
ハイブリッド環境で Skype ルームのシステムを展開する方法の詳細については、このトピックを参照してください。
  
## <a name="hybrid-deployments"></a>ハイブリッド展開

トポロジでは、Skype を持つビジネス サーバーおよび Exchange Online では、Exchange Online で Skype ルームのシステム リソースのメールボックスをホストする場合は、以下の手順を実行します。 またこのセクションでは、Exchange Online と Exchange Server の両方が展開されているハイブリッドのシナリオについて説明します。
  
、例示目的でオンラインのドメインのドメインの設置と LyncSample.ccstp.net の LyncSample.com を使用します。
  
1. Exchange のオンラインでの準備の説明に従ってオンラインでの Exchange 管理シェルに接続することによって、Exchange 管理センター (LyncSample.ccsctp.net) でリソース メールボックスを作成します。
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    ログに記録する lrstest5@LyncSample.ccsctp.net を使用して OWA の接続を確認できます。
    
2. Office 365 の Exchange 管理センターで、電子メールのアドレス lrstest5@LyncSample.com (prem のドメイン) を追加し、返信アドレスとして設定します。
    
3. Prem で Active Directory のユーザー lrstest5@LyncSample.com を作成、lrstest5@LyncSample.com に電子メール アドレスの設定し、ターゲット アドレスを lrstest5@LyncSample.com に設定します。
    
4. ディレクトリの同期をトリガーし、同期が完了した後ことを確認ユーザーが AAD でマージする Office365 Exchange 管理センターでの受信者のリソースのプロパティを変更することがないこと。
    
5. Lrstest5@LyncSample.com を使用して OWA の接続を確認します。(以前のバージョンでは、することを確認、オンラインのドメインを使用して OWA 接続。)
    
    メールボックスを作成した後、Exchange Online 管理シェルで Set-CalendarProcessing を使用してメールボックスを構成できます。詳細については、単一フォレストのオンプレミス展開の手順 3 ～ 6 を参照してください。
    
    > [!NOTE]
    > Exchange Server および Exchange Online を使用して、ハイブリッド環境を使っている場合に、Exchange 管理シェルと有効にする RemoteMailbox の lrstest5@LyncSample.com ・ RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net ・ ルーム。 ディレクトリ同期をトリガーします。 
  
    オンライン Exchange Skype ルームのシステム メールボックスをホストする場合は、Exchange 管理シェルの手順は必須ではありませんし、手順 6 に進むことができます。
    
6. Skype のビジネス管理シェルの次のコマンドレットを実行して、ビジネスの Skype の Skype ルームのシステム アカウントを有効にします。
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> あれば Skype の Skype ではなくビジネス オンライン ビジネス サーバーの上記のシナリオは、Exchange リソース メールボックスをプロビジョニングした後、Skype のビジネスのオンライン提供、Skype で説明したようにビジネス アカウントを準備します。 
  

