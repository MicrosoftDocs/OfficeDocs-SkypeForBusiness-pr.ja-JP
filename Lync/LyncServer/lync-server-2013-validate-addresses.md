---
title: 住所の確認
TOCTitle: 住所の確認
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48273226
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 住所の確認

 

_**トピックの最終更新日:** 2012-09-17_

場所データベースを公開する前に、SIP トランクまたは公衆交換電話網 (PSTN) E9-1-1 サービス プロバイダーが維持する主要道路住所案内 (MSAG) で新しい場所を確認する必要があります。

SIP トランク E9-1-1 サービス プロバイダーの詳細については、「[Lync Server 2013 の E9-1-1 サービス プロバイダーの選択](lync-server-2013-choosing-an-e9-1-1-service-provider.md)」を参照してください。

住所の確認の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

## 場所データベースにある住所を確認するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のコマンドレットを実行して、緊急サービス プロバイダーとの接続を構成します。
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  次のコマンドレットを実行して、場所データベース内の住所を確認します。
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    また、**Test-CsLisCivicAddress** コマンドレットを使用して、個々の住所を確認することもできます。

