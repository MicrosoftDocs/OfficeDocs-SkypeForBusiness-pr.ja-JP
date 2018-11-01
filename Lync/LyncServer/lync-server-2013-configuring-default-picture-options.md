---
title: 既定のピクチャ オプションの構成
TOCTitle: 既定のピクチャ オプションの構成
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn205074(v=OCS.15)
ms:contentKeyID: 53901568
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既定のピクチャ オプションの構成

 

_**トピックの最終更新日:** 2013-03-22_

既定では、ユーザーの写真が自動的に表示されます。ユーザーが写真を非表示にしたい場合は、Lync クライアントの \[**写真を表示しない**\] オプションを選択できます。ただし、この設定は他の一部の Office アプリケーションでは無視されます。

ユーザーが表示をオフにしても写真が表示される可能性が問題になる場合は、Lync の写真表示設定をグローバルに変更するか、サイトまたはサービスに対して変更して、ユーザーの写真が既定で表示されないようにすることができます。次の Lync Server 管理シェル コマンドレットを使用して、ユーザーがクライアントで \[**写真を表示する**\] オプションを明示的に選択しない限り、ユーザーの写真が表示されないようにすることができます。

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

このコマンドレットの詳細については、Lync Server 管理シェル ドキュメントの「[Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)」を参照してください。

