---
title: Lync 2013 のグループ ポリシー設定
TOCTitle: Lync 2013 のグループ ポリシー設定
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48272193
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 のグループ ポリシー設定

 

_**トピックの最終更新日:** 2016-12-08_

Lync および Office Communicator の以前のバージョンでは、クライアント グループ ポリシー設定を構成するために、スタンドアロンの Communicator.adm 管理用テンプレートを使用できました。Lync 2013 では、Office グループ ポリシー管理用テンプレートと共に、新しい管理用テンプレート ファイル (.admx ファイルと .adml ファイル) が用意されています。Lync 2013 の .admx ファイルと .adml ファイルを使用すると、テンプレートをダウンロードし、すべての Office プログラムと言語パックのグループ ポリシー設定を一元管理できます。詳細については、Office 2013 ドキュメントの Office 2013 管理用テンプレート ファイル (ADMX、ADML) に関するページ ([http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0x411)) を参照してください。

## クライアント ブートストラップ ポリシー

ユーザーが初めてサーバーにサインインする前に、幾つかのクライアント ブートストラップ ポリシーを構成する必要があります。これらのポリシーは、クライアントがサインインする前に有効になり、サーバーからインバンド プロビジョニング設定を受け取るようになるため、グループ ポリシーを使って構成できます。詳細については、「展開」のドキュメントの「[Lync Server 2013 でのクライアント ブートストラップ ポリシーの構成](lync-server-2013-configuring-client-bootstrapping-policies.md)」を参照してください。

