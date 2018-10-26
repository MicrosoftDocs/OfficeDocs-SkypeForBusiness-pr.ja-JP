---
title: Lync Server 2013 でのサイト レベルのホスト ボイス メール ポリシーの作成
TOCTitle: Lync Server 2013 でのサイト レベルのホスト ボイス メール ポリシーの作成
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48271349
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのサイト レベルのホスト ボイス メール ポリシーの作成

 

_**トピックの最終更新日:** 2012-09-24_

サイト ポリシーは、このポリシーが定義されているサイトに所属するすべてのユーザーに影響します。 Hosted Exchange UM にアクセスできるように構成されているユーザーにユーザー単位のポリシーが割り当てられていない場合には、サイト ポリシーが適用されます。 サイト ポリシーを展開してない場合は、グローバル ポリシーが適用されます。

サイト ポリシーの構成の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## サイトのホスト ボイス メール ポリシーを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  New-CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。 たとえば、以下を実行します。
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    この例では、サイト スコープを使用してホスト ボイス メール ポリシーを作成し、次のパラメーターを設定しています。
    
      - **Identity** では、ポリシーの一意の識別子を指定します。これにはスコープも含まれます。 サイト スコープを使用するポリシーの場合、Identity パラメーターの値は `site:`\<名前\> の形式で指定する必要があります (`site:Redmond` など)。
    
      - **Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。
    
      - **Description** では、ポリシーに関する説明情報を指定します (オプション)。
    
      - **Organization** では、Lync Server 2013 ユーザーが所属する Exchange テナントのコンマ区切り一覧を指定します。各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。

