---
title: 'ビジネス サーバーの Skype での統合連絡先ストアを展開します。 '
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '概要: は、Skype のビジネス サーバーの統合連絡先ストアを有効にします。'
ms.openlocfilehash: 5e7fb34d03459be5066d154e89fa8e27dc060757
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219623"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>ビジネス サーバーの Skype での統合連絡先ストアを展開します。
 
**の概要:** Skype のビジネス サーバーの統合連絡先ストアを有効にします。
  
ビジネス サーバーの Skype での統合連絡先ストアを有効にするとしても、任意のトポロジ設定は不要です。 ユーザーに対して統合連絡先ストアを有効にするには、次の条件が必要です。
  
- 統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。
    
- ユーザーのログオン ビジネス用の Skype で少なくとも 1 回。
    
ユーザーの連絡先を移行した後、ビジネスの Skype を使用してユーザーのログオン時に自動的に行われますユーザーはアクセスし、ビジネス、2013 年 Outlook または Outlook Web Access の Skype からビジネス用連絡先に、Skype を管理できます。 ユーザーは、Outlook または Outlook Web Access からこれらの連絡先を管理するためにビジネス用の Skype にログインするのにはありません。
  
> [!IMPORTANT]
> ユーザーのログオン ビジネス用の Skype からの移行後、利用可能で、最新の状態は、連絡先およびグループが、ユーザー (つまり、追加、削除、移動、タグ、タグ、または変更) を管理することはできませんそれらの連絡先です。 
  
## <a name="enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にする

Skype をビジネスのサーバーの展開トポロジを公開すると、統合連絡先ストアはすべてのユーザーに対して既定で有効。 にします。 Skype ビジネス サーバーの展開後は、統合連絡先ストアを有効にする追加アクションを実行する必要はありません。 ただし、**Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。 この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。
  
### <a name="to-enable-users-for-unified-contact-store"></a>統合連絡先ストアでユーザーを有効にするには

1. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスの Skype**をクリック**ビジネス サーバー管理シェルの Skype**です。
    
2. 次のいずれかの操作を実行します。
    
   - ビジネス サーバーのユーザーのすべての Skype のグローバルの統合連絡先ストアを有効にするには、Windows PowerShell のコマンド ライン インターフェイスで次のコマンドレットを間します。
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 統合連絡先ストアを特定のサイトのユーザーに対して有効にするには、プロンプトで次のように入力します。
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   次に例を示します。
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 統合連絡先ストアをテナントごとに有効にするには、プロンプトで次のように入力します。
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例:
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 統合連絡先ストアを特定のユーザーに対して有効にするには、プロンプトで次のように入力します。
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。 
  
    例:
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 上の例では、最初のコマンドは、UCS の有効なユーザーの名前を UcsAllowed フラグを True に設定が、新しいユーザーごとのポリシーを作成します。 2 番目のコマンドでは、Ken Myer は、Ken Myer が有効になったことは、統合連絡先ストアの表示名のユーザーにポリシーが割り当てられます。
  
## <a name="migrate-users-to-unified-contact-store"></a>統合連絡先ストアへのユーザーの移行

ユーザーの連絡先は、Exchange 2013 サーバーに自動的に移行するとき、ユーザー。
  
- UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。
    
- Exchange 2013 メールボックスに準備されているしにサインインして、メールボックスに少なくとも 1 回。
    
- リッチ クライアントのビジネスを Skype を使用してにログオンします。
    
Lync または以前のクライアントを使用して、ユーザーがログオンした場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合は、ユーザー サービス ポリシーは無視され、ユーザーの連絡先に保存しておく Skype ビジネス サーバー。
  
ユーザーの連絡先が移行されているかどうかは、次のいずれかの方法で確認できます。 
  
- クライアント コンピューターで次のレジストリ キーを調べます。
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS
    
    Exchange 2013 では、ユーザーの連絡先が保存されている場合、このキーには、2165 の値を持つには、InUCSMode の値が含まれています。
    
- **Test-CsUnifiedContactStore** コマンドレットを実行します。 ビジネス サーバー管理シェル コマンド ラインの Skype で次のように入力します。
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    **Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。
    
## <a name="roll-back-migrated-users"></a>移行したユーザーのロールバック

ロールバックする必要がある場合は、統合連絡先ストアの機能を元に戻す、連絡先、ユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ。 ロールバックし、ユーザーのポリシーを無効にする**呼び出し CsUcsRollback**コマンドレットを実行し、します。 **呼び出し CsUcsRollback**だけを実行するだけではありません、永続的なロールバックを確認するのに十分な統合連絡先ストアの移行が再び開始されるポリシーが無効になっていない場合。 などの場合は、ユーザーがいるために、ロールバック Exchange 2010 を Exchange 2013 がロールバックされ、ユーザーのメールボックスを Exchange 2013 に移動し、統合連絡先ストアの移行が開始される、ロールバックした後、再び 7 日間統一された取引先担当者を保存する場合に限りユーザー サービス ポリシーでユーザーにも有効です。
  
**移動 CsUser**コマンドレットを自動的にロールバック連絡先ストアのユーザーの Exchange 2013 から Skype をビジネス サーバーの次のような場合。
  
- ユーザーを移動するとき Skype からビジネスのサーバーに Microsoft Lync Server 2013 または Lync Server 2010 にします。 
    
- 設置型の場合は、ユーザーを移動するとき Skype のオンライン ビジネスの Skype をビジネス サーバー設置型など、相互のユーザーを移行するとき、またはその逆。
    
バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。
  
- ユーザーの連絡先は、Exchange 2013 に移行し、次に、移行後、同じデータをインポートする前に、連絡先リストをエクスポートする場合は、統合連絡先ストアのデータと連絡先の一覧が破損します。
    
- Exchange 2013 にユーザーを移行した後にユーザーのデータをエクスポートする場合、移行をロールバックし、何らかの理由は、移行後のデータをインポートする、統合された連絡先データを格納および連絡先リストが破損しています。
    
> [!IMPORTANT]
> Exchange 2010 を Exchange 2013 から Exchange メールボックスを移動する前に Exchange 管理者は必ず、ビジネス サーバー管理者の Skype 最初ロール ・ バックされたビジネス サーバー ユーザーの連絡先を Skype Exchange 2013 の Skype にビジネス サーバーです。 統合連絡先ストアの連絡先にロールバック Skype ビジネス サーバーに対して、手順を参照して統合連絡先ストアの連絡先を Exchange 2013 に Skype for ビジネス サーバーからロールバック"するには」後でこのセクションで。 
  
 **ユーザーの連絡先をロールバックする方法:****移動 CsUser**コマンドレットが自動的にロールバック統合連絡先ストアの Skype からユーザーを移動するため、これらの手順をスキップできますビジネス サーバー 2015 の Skype と Lync Server 2010 のユーザーを移動する**移動 CsUser**コマンドレットを使用する場合Lync Server 2010 サーバー 2015 ビジネスです。 **Csuser からの移動**は無効に統合連絡先ストア ポリシー、ユーザーに戻して Skype ビジネス サーバー 2015 の場合、統合連絡先ストアへの移行が繰り返されるようにします。
  

