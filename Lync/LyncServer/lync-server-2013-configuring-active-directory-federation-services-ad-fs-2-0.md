---
title: Active Directory フェデレーション サービス (AD FS 2.0) の構成
TOCTitle: Active Directory フェデレーション サービス (AD FS 2.0) の構成
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn308561(v=OCS.15)
ms:contentKeyID: 56270048
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Active Directory フェデレーション サービス (AD FS 2.0) の構成

 

_**トピックの最終更新日:** 2016-12-08_

次のセクションでは、多要素認証をサポートするように Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。AD FS 2.0 のインストール方法については、AD FS 2.0 のステップバイステップ ガイドとハウツー ガイド ([http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)) を参照してください。

> [!NOTE]
> AD FS 2.0 をインストールするときは、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しないでください。代わりに、Active Directory フェデレーション サービス 2.0 RTW パッケージを <a href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</a> からダウンロードしてインストールします。



**2 要素認証の AD FS を構成するには**

1.  ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2.  Windows PowerShell を起動します。

3.  Windows PowerShell コマンド ラインで次のコマンドを実行します。
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  次のコマンドを実行して、パッシブ認証に対して有効にされる、2013 年 7 月のディレクター、エンタープライズ プール、Standard Edition サーバー向け Lync Server 2013 累積更新プログラムを適用した各 Lync Server 2013 サーバーとパートナーシップを確立します。サーバー名は、実際の展開の固有名に置き換えてください。
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  \[管理ツール\] メニューから AD FS 2.0 管理コンソールを起動します。

6.  \[**信頼関係**\]、\[**証明書利用者の信頼**\] の順に展開します。

7.  2013 年 7 月のエンタープライズ プールまたは Standard Edition サーバー向け Lync Server 2013 累積更新プログラムを適用した Lync Server 2013 に、新しい信頼が作成されたことを確認します。

8.  Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行承認規則を作成して割り当てます。
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'

    &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules

9.  Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行変換規則を作成して割り当てます。
    
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules

10. AD FS 2.0 管理コンソールで、証明書利用者の信頼を右クリックし、\[**要求規則の編集**\] をクリックします。

11. \[**発行承認規則**\] タブをクリックし、新しい承認規則が正しく作成されたことを確認します。

12. \[**発行変換規則**\] タブをクリックし、新しい変換規則が正しく作成されたことを確認します。

