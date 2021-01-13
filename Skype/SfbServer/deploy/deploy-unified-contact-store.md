---
title: 'Skype for Business Server での統合連絡先ストアの展開 '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '概要: Skype for Business Server で統合連絡先ストアを有効にします。'
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812557"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Skype for Business Server での統合連絡先ストアの展開
 
**概要:** Skype for Business Server で統合連絡先ストアを有効にします。
  
Skype for Business Server で統合連絡先ストアを有効にする場合、トポロジ設定は必要ではありません。 ユーザーの統合連絡先ストアを有効にするには:
  
- 統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。
    
- ユーザーは少なくとも 1 回は Skype for Business でログインします。
    
ユーザーの連絡先が移行された後、ユーザーは Skype for Business にログインすると自動的に行われます。ユーザーは、Skype for Business、Outlook 2013、または Outlook Web Access から Skype for Business の連絡先にアクセスして管理できます。 ユーザーは、Outlook または Outlook Web Access から連絡先を管理するために Skype for Business にログインする必要があります。
  
> [!IMPORTANT]
> 移行後にユーザーが Skype for Business からログインした場合、連絡先とグループは使用可能で最新の情報に更新されますが、ユーザーはそれらの連絡先を管理 (追加、削除、移動、タグ付け、タグ解除、または変更) できません。 
  
## <a name="enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にする

Skype for Business Server を展開してトポロジを公開すると、統合連絡先ストアは既定ですべてのユーザーに対して有効になります。 Skype for Business Server の展開後に統合連絡先ストアを有効にする追加のアクションを実行する必要はありません。 ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。 この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。
  
### <a name="to-enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にするには

1. Skype for Business Server 管理シェルを起動します **。[スタート**] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
2. 次のどちらかの操作を行います。
    
   - すべての Skype for Business Server ユーザーに対して統合連絡先ストアをグローバルに有効にするには、コマンド ライン インターフェイスの Windows PowerShellコマンドレットを使用します。
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 特定のサイトのユーザーに対して統合連絡先ストアを有効にするには、プロンプトで次のコマンドを入力します。
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   例:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - テナント別に統合連絡先ストアを有効にするには、プロンプトで次のコマンドを入力します。
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 特定のユーザーに対して統合連絡先ストアを有効にするには、プロンプトで次のコマンドを入力します。
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。 
  
    例:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 前の例では、最初のコマンドで UcsAllowed フラグが True に設定された UCS Enabled Users という名前の新しいユーザーごとのポリシーを作成します。 2 番目のコマンドは、Ken Myer という表示名を持つユーザーにポリシーを割り当て、Ken Myer が統合連絡先ストアに対して有効になっているという意味です。
  
## <a name="migrate-users-to-unified-contact-store"></a>統合連絡先ストアへのユーザーの移行

次の場合、ユーザーの連絡先は Exchange 2013 サーバーに自動的に移行されます。
  
- UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。
    
- Exchange 2013 メールボックスでプロビジョニングされ、少なくとも 1 回はメールボックスにサインインしています。
    
- ユーザーが Skype for Business リッチ クライアントを使用してログインした場合。
    
ユーザーが Lync 以前のクライアントでログインした場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザーのサービス ポリシーは無視され、ユーザーの連絡先は Skype for Business Server に残ります。
  
ユーザーの連絡先が移行されているかどうかは、次のどちらかの方法で確認できます。 
  
- クライアント コンピューターで次のレジストリ キーを調べます。
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ SIP URL \> \UCS
    
    ユーザーの連絡先が Exchange 2013 に保存されている場合、このキーには、値 2165 の InUCSMode の値が含まれる。
    
- **Test-CsUnifiedContactStore** コマンドレットを実行します。 Skype for Business Server 管理シェル コマンド ラインで、次のコマンドを入力します。
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    **Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。
    
## <a name="roll-back-migrated-users"></a>移行したユーザーをロールバックする

統合連絡先ストア機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ、連絡先をロールバックします。 ロールバックするには、ユーザーのポリシーを無効にし **、Invoke-CsUcsRollback コマンドレットを実行** します。 **Invoke-CsUcsRollback** を単独で実行するだけでは、永続的なロールバックを保証するには十分ではありません。ポリシーが無効にされていない場合は、統合連絡先ストアの移行が再び開始されます。 たとえば、Exchange 2013 が Exchange 2010 にロールバックされ、そのユーザーのメールボックスが Exchange 2013 に移動されたため、ユーザーがロールバックされた場合、統合連絡先ストアの移行はロールバックの 7 日後に再び開始されます。ユーザー サービス ポリシーで統合連絡先ストアがユーザーに対して有効な場合です。
  
**Move-CsUser コマンドレット** は、次の状況で、ユーザーの連絡先ストアを Exchange 2013 から Skype for Business Server に自動的にロールバックします。
  
- ユーザーが Skype for Business Server から Microsoft Lync Server 2013 または Lync Server 2010 に移動される場合。 
    
- ユーザーが Skype for Business Online からオンプレミスの Skype for Business Server に、またはその逆に移動された場合など、ユーザーがクロスオンプレミスに移行される場合。
    
バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。
  
- ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートし、移行後に同じデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。
    
- ユーザーを Exchange 2013 に移行した後にユーザー データをエクスポートする場合は、移行をロールバックし、移行後に何らかの理由でデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。
    
> [!IMPORTANT]
> Exchange メールボックスを Exchange 2013 から Exchange 2010 に移動する前に、Exchange 管理者は、Skype for Business Server 管理者が最初に Skype for Business Server のユーザー連絡先を Exchange 2013 から Skype for Business Server にロールバックする必要があります。 統合連絡先ストアの連絡先を Skype for Business Server にロールバックするには、このセクションの後半の「統合連絡先ストアの連絡先を Exchange 2013 から Skype for Business Server にロールバックするには」の手順を参照してください。 
  
 **ユーザーの連絡先をロールバックする方法:****Move-CsUser** コマンドレットを使用して Skype for Business Server 2015 と Lync Server 2010 の間でユーザーを移動する場合 **、Move-CsUser** コマンドレットは、Skype for Business Server 2015 から Lync Server 2010 にユーザーを移動するときに統合連絡先ストアを自動的にロールバックします。 **Move-CsUser** は統合連絡先ストア ポリシーを無効にしないので、ユーザーが Skype for Business Server 2015 に戻された場合、統合連絡先ストアへの移行が再び実行されます。
  

