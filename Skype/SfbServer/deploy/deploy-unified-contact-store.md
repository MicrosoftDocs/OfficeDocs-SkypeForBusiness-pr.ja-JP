---
title: '統合連絡先ストアを展開Skype for Business Server '
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '概要: 連絡先ストアで統合連絡先ストアを有効Skype for Business Server。'
---

# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>統合連絡先ストアを展開Skype for Business Server
 
**概要:**[連絡先] で統合連絡先ストアを有効Skype for Business Server。
  
統合連絡先ストアを Skype for Business Serverトポロジの設定は必要とされません。 ユーザーに対して統合連絡先ストアを有効にするには、次の方法を使用します。
  
- 統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。
    
- ユーザーは、少なくとも 1 Skype for Businessを使用してログインします。
    
ユーザーの連絡先が移行された後、ユーザーが Skype for Business でログインすると自動的に行われます。ユーザーは Skype for Business、Outlook 2013、または Outlook Web Access から Skype for Business 連絡先にアクセスして管理できます。 ユーザーは、Web Access から連絡先を管理するために、Skype for BusinessにログインするOutlook必要Outlook必要があります。
  
> [!IMPORTANT]
> ユーザーが移行後に Skype for Business からログインした場合、連絡先とグループは利用可能で最新の情報を提供されますが、ユーザーはそれらの連絡先を管理できません (つまり、追加、削除、移動、タグ付け、タグ解除、または変更)。 
  
## <a name="enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にする

トポロジを展開Skype for Business Server、統合連絡先ストアは既定ですべてのユーザーに対して有効になっています。 展開後に統合連絡先ストアを有効にするには、追加のアクションを実行するSkype for Business Server。 ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。 この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。
  
### <a name="to-enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にするには

1. [管理シェルSkype for Business Server起動する **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
2. 次のどちらかの操作を行います。
    
   - すべてのユーザーに対して統合連絡先ストアSkype for Business Server有効にするには、コマンド ライン インターフェイスで次Windows PowerShellを実行します。
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 特定のサイトのユーザーに対して統合連絡先ストアを有効にするには、プロンプトで次の入力を行います。
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   次に例を示します。
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - テナント別に統合連絡先ストアを有効にするには、プロンプトで次の入力を行います。
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   次に例を示します。
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 特定のユーザーに対して統合連絡先ストアを有効にするには、プロンプトに次の入力を入力します。
    
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
    > 前記の例の最初のコマンドでは、UcsAllowed フラグを True に設定することで、新しいユーザーごとのポリシーを UCS Enabled Users という名前で作成しています。2 番目のコマンドでは、Ken Myer という表示名のユーザーにこのポリシーを割り当てています。これは、Ken Myer が統合連絡先ストアで有効になったことを意味します。
  
## <a name="migrate-users-to-unified-contact-store"></a>ユーザーを統合連絡先ストアに移行する

次の場合、ユーザーの連絡先は Exchange 2013 サーバーに自動的に移行されます。
  
- UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。
    
- 2013 年 2013 年Exchangeで準備され、少なくとも 1 回はメールボックスにサインインしています。
    
- ユーザーが Skype for Business リッチ クライアントを使用してログインした場合。
    
ユーザーが Lync または以前のクライアントでログインした場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザー サービス ポリシーは無視され、ユーザーの連絡先は Skype for Business Server に残ります。
  
ユーザーの連絡先が移行されているかどうかは、次のどちらかの方法で確認できます。 
  
- クライアント コンピューターで次のレジストリ キーを調べます。
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ SIP URL\>\UCS
    
    ユーザーの連絡先が Exchange 2013 に格納されている場合、このキーには値 2165 の InUCSMode が含まれる。
    
- **Test-CsUnifiedContactStore** コマンドレットを実行します。 [管理シェルSkype for Business Server] コマンド ラインで、次のコマンドを入力します。
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    **Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。
    
## <a name="roll-back-migrated-users"></a>移行されたユーザーのロールバック

統合連絡先ストア機能をロールバックする必要がある場合は、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ連絡先をロールバックします。 ロールバックするには、ユーザーのポリシーを無効にし、 **Invoke-CsUcsRollback コマンドレットを実行** します。 **Invoke-CsUcsRollback** を単独で実行するだけでは、ポリシーが無効にされていない場合に統合連絡先ストアの移行が再び開始されますので、永続的なロールバックを確保するには十分ではありません。 たとえば、Exchange 2013 が Exchange 2010 にロールバックされ、ユーザーのメールボックスが Exchange 2013 に移動されたため、ユーザーがロールバックされた場合、統合連絡先ストアの移行は、ユーザー サービス ポリシーのユーザーに対して引き続き有効になっている限り、ロールバックの 7 日後に再度開始されます。
  
**Move-CsUser** コマンドレットは、次の状況で、ユーザーの連絡先ストアを 2013 Exchange からSkype for Business Server自動的にロールバックします。
  
- ユーザーが Microsoft Lync Server 2013 Skype for Business Server Lync Server 2010 に移動された場合。 
    
- ユーザーがクロスオンプレミスに移行される場合 (ユーザーがオンラインからオンプレミスに移動Skype for Business場合Skype for Business Server、その逆も同様です。
    
バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。
  
- ユーザーの連絡先が Exchange 2013 に移行される前に連絡先リストをエクスポートし、移行後に同じデータをインポートすると、統合連絡先ストア のデータと連絡先リストが破損します。
    
- ユーザーを Exchange 2013 に移行した後にユーザー データをエクスポートする場合は、移行をロールバックし、移行後に何らかの理由でデータをインポートすると、統合連絡先ストア のデータと連絡先リストが破損します。
    
> [!IMPORTANT]
> Exchange メールボックスを Exchange 2013 から Exchange 2010 に移動する前に、Exchange 管理者は、Skype for Business Server 管理者が最初にSkype for Business Server 2013 Exchangeからユーザーの連絡先Skype for Business Server。 統合連絡先ストアの連絡先を Skype for Business Server にロールバックするには、このセクションの「統合連絡先ストアの連絡先を Exchange 2013 から Skype for Business Server にロールバックするには」の手順を参照してください。 
  
 **ユーザーの連絡先をロールバックする方法:** Move-CsUser コマンドレットを使用してユーザーを Skype for Business Server 2015 と Lync Server 2010 の間で移動する場合、**Move-CsUser** コマンドレットは、ユーザーを  Skype for Business Server 2015 から Lync Server 2010 に移動するときに統合連絡先ストアを自動的にロールバックしますので、これらの手順を省略できます。 **Move-CsUser** は統合連絡先ストア ポリシーを無効にしないので、ユーザーが 2015 年に戻った場合、統合連絡先ストアへの移行はSkype for Business Serverされます。
  

