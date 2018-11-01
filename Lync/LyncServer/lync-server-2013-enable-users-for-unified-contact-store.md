---
title: 'Lync Server 2013: 統合連絡先ストアでユーザーを有効にする'
TOCTitle: 統合連絡先ストアでユーザーを有効にする
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48272611
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の統合連絡先ストアでユーザーを有効にする

 

_**トピックの最終更新日:** 2012-10-07_

Lync Server 2013 を展開してトポロジを公開すると、既定で統合連絡先ストアがすべてのユーザーに対して有効になります。 Lync Server 2013 を展開した後で統合連絡先ストアを有効にするために特別な作業を行う必要はありません。ただし、 **Set-CsUserServicesPolicy** コマンドレットを使用すると、どのユーザーが統合連絡先ストアを使用できるのかをカスタマイズできます。この機能の有効化は、グローバルに行うことも、サイトごと、テナントごと、または個人やそのグループごとに行うこともできます。

## 統合連絡先ストアでユーザーを有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のいずれかの操作を行います。
    
      - 統合連絡先ストアをすべての Lync Server ユーザーに対してグローバルに有効にするには、コマンドラインで次のように入力します。
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 統合連絡先ストアを特定のサイトのユーザーに対して有効にするには、コマンドラインで次のように入力します。
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        次に例を示します。
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 統合連絡先ストアをテナントごとに有効にするには、コマンドラインで次のように入力します。
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        次に例を示します。
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 統合連絡先ストアを特定のユーザーに対して有効にするには、コマンドラインで次のように入力します。
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        > [!NOTE]  
        > ユーザーの表示名の代わりに、ユーザー エイリアスや SIP URI を使用することもできます。
        
        次に例を示します。
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        > [!NOTE]  
        > 前記の例の最初のコマンドでは、UcsAllowed フラグを True に設定することで、新しいユーザーごとのポリシーを <em>UCS Enabled Users</em> という名前で作成しています。2 番目のコマンドでは、Ken Myer という表示名のユーザーにこのポリシーを割り当てています。これは、Ken Myer が統合連絡先ストアで有効になったことを意味します。

