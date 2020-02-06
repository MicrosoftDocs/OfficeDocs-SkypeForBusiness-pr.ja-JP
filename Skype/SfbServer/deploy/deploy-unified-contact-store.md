---
title: 'Skype for Business Server にユニファイド連絡先ストアを展開する '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '概要: Skype for Business Server でユニファイド連絡先ストアを有効にします。'
ms.openlocfilehash: 382b4ed059c4066ae862bb3fe24b98b4bdde2a18
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798094"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Skype for Business Server にユニファイド連絡先ストアを展開する
 
**概要:** Skype for Business Server でユニファイド連絡先ストアを有効にします。
  
Skype for Business Server で統合連絡先ストアを有効にするには、トポロジ設定は必要ありません。 ユーザーに対して統合連絡先ストアを有効にするには、次の条件が必要です。
  
- 統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。
    
- ユーザーは、少なくとも1回は Skype for Business でログインします。
    
ユーザーが Skype for business を使ってログインしたときに自動的に実行されるユーザーの連絡先が移行された後、ユーザーは skype for Business、Outlook 2013、または Outlook Web Access から Skype for Business の連絡先にアクセスして管理することができます。 ユーザーは、Outlook または Outlook Web Access から連絡先を管理するために、Skype for Business にログインする必要はありません。
  
> [!IMPORTANT]
> ユーザーが移行後に Skype for Business からログインした場合、連絡先とグループは最新の状態になっていますが、ユーザーはその連絡先を管理 (追加、削除、移動、タグ付け、解除、または変更) することはできません。 
  
## <a name="enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にする

Skype for Business Server を展開してトポロジを公開すると、既定では、統合連絡先ストアがすべてのユーザーに対して有効になります。 統合連絡先ストアを有効にするには、Skype for Business Server を展開した後で、追加の操作を行う必要はありません。 ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。 この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。
  
### <a name="to-enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にするには

1. Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype For business**]、[ **skype for business server 管理シェル**] の順にクリックします。
    
2. 次のいずれかの操作を実行します。
    
   - すべての Skype for Business Server ユーザーに対して、統合された連絡先ストアをグローバルに有効にするには、Windows PowerShell コマンドラインインターフェイスで次のコマンドレットを実行します。
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 統合連絡先ストアを特定のサイトのユーザーに対して有効にするには、プロンプトで次のように入力します。
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   次に例を示します。
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 統合連絡先ストアをテナントごとに有効にするには、プロンプトで次のように入力します。
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 統合連絡先ストアを特定のユーザーに対して有効にするには、プロンプトで次のように入力します。
    
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
    > 上の例では、最初のコマンドは、UcsAllowed フラグが True に設定された、UCS を有効にしたユーザーという新しいユーザーごとのポリシーを作成します。 2番目のコマンドは、[Ken Myer] と表示されているユーザーにポリシーを割り当てます。この場合は、Ken Myer がユニファイド連絡先ストアに対して有効になっていることを意味します。
  
## <a name="migrate-users-to-unified-contact-store"></a>統合連絡先ストアへのユーザーの移行

ユーザーの連絡先は、ユーザーが次のように Exchange 2013 サーバーに自動的に移行されます。
  
- UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。
    
- は Exchange 2013 メールボックスでプロビジョニングされ、少なくとも1回はメールボックスにサインインしています。
    
- Skype for Business リッチクライアントを使用してログインします。
    
ユーザーが Lync または以前のクライアントを使ってログインしている場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザーサービスポリシーは無視され、ユーザーの連絡先は Skype for Business Server に残ります。
  
ユーザーの連絡先が移行されているかどうかは、次のいずれかの方法で確認できます。 
  
- クライアント コンピューターで次のレジストリ キーを調べます。
    
    HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\ UCS
    
    ユーザーの連絡先が Exchange 2013 に保存されている場合、このキーには2165の値を持つ InUCSMode の値が格納されます。
    
- **Test-CsUnifiedContactStore** コマンドレットを実行します。 Skype for Business Server 管理シェルコマンドラインで、次のように入力します。
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    **Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。
    
## <a name="roll-back-migrated-users"></a>移行したユーザーのロールバック

ユニファイド連絡先ストアの機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ、連絡先をロールバックします。 ロールバックするには、ユーザーのポリシーを無効にしてから、 **CsUcsRollback**コマンドレットを実行します。 **CsUcsRollback**のみを実行するだけでは、ポリシーが無効になっている場合に、統合された連絡先ストアの移行が再び開始されるため、永続的なロールバックを確実に行うことはできません。 たとえば、exchange 2013 が Exchange 2010 にロールバックされたためにユーザーがロールバックされた場合、ユーザーのメールボックスは Exchange 2013 に移動されます。統合連絡先ストアの移行は、統合連絡先ストアの場合、ロールバック後7日後に開始されます。は、ユーザーサービスポリシーのユーザーに対してまだ有効になっています。
  
**ムーブグループのユーザー**コマンドレットは、次のような場合に、ユーザーの連絡先ストアを Exchange 2013 から Skype For business Server に自動的にロールバックします。
  
- ユーザーが Skype for Business Server から Microsoft Lync Server 2013 または Lync Server 2010 に移動された場合。 
    
- ユーザーが Skype for Business Online からオンプレミスの Skype for Business Server に移行された場合、またはその逆の場合など、ユーザーがクロスオンプレミスに移行された場合。
    
バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。
  
- ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートした後、移行後に同じデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。
    
- Exchange 2013 にユーザーを移行した後にユーザーデータをエクスポートする場合は、移行をロールバックし、なんらかの理由で移行後にデータをインポートすると、統合連絡先ストアのデータと連絡先リストが破損します。
    
> [!IMPORTANT]
> Exchange のメールボックスを exchange 2013 から Exchange 2010 に移動する前に、Exchange 管理者が、skype for business server のユーザー連絡先を Exchange 2013 から Skype にロールバックしていることを確認する必要があります。Business Server。 ユニファイド連絡先ストアの連絡先を Skype for Business Server にロールバックするには、このセクションの後半の「ユニファイド連絡先ストアの連絡先を Exchange 2013 から Skype for Business Server にロールバックする」の手順を参照してください。 
  
 **ユーザーの連絡先をロールバックする方法を教えてください。****ムーブグループユーザーコマンドレットを**使用して、Skype for business server 2015 と lync server 2010 の間でユーザーを移動する場合は、ユーザーが Skype For business server 2015 から lync server 2010 に**移行した**ときに、次の手順をスキップできます。 **ムーブグループユーザー**は、ユニファイド連絡先ストアポリシーを無効にしないため、ユーザーを Skype For business Server 2015 に戻すと、統合連絡先ストアへの移行が繰り返されます。
  

