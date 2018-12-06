---
title: カスタマイズされた常設チャット サーバーのコンプライアンス アダプターに XmlAdapter を置き換える
TOCTitle: カスタマイズされた常設チャット サーバーのコンプライアンス アダプターに XmlAdapter を置き換える
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49886893
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# カスタマイズされた常設チャット サーバーのコンプライアンス アダプターに XmlAdapter を置き換える

 

_**トピックの最終更新日:** 2012-11-01_

常設チャット サーバーと共にインストールされる XmlAdapter を使用する代わりに、カスタム アダプターを記述できます。カスタム アダプターを記述するには、**IComplianceAdapter** インターフェイスを実装するパブリック クラスを含む .NET Framework アセンブリを提供する必要があります。このアセンブリは、常設チャット サーバー プールの各サーバーの常設チャット サーバー インストール フォルダー内に配置する必要があります。任意のコンプライアンス サーバーからアダプターにコンプライアンス データを提供できますが、コンプライアンス サーバーからアダプターの複数のインスタンスに対して重複するコンプライアンス データを提供することはできません。

## IComplianceAdapter インターフェイスの実装

このインターフェイスは、名前空間 `Microsoft.Rtc.Internal.Chat.Server.Compliance` の Compliance.dll アセンブリに定義されています。このインターフェイスには、カスタム アダプターが実装する必要のある 2 つのメソッドが定義されています。

    void SetConfig(AdapterConfig config)

常設チャット コンプライアンス サーバーは、アダプターが最初に読み込まれたときにこのメソッドを呼び出します。`AdapterConfig` には、コンプライアンス アダプターに関連する常設チャット コンプライアンス構成が含まれています。

    void Translate(ConversationCollection conversations)

常設チャット コンプライアンス サーバーは、変換する新しいデータが存在する間、定期的にこのメソッドを呼び出します。呼び出し間隔は、常設チャット コンプライアンス構成に設定された `RunInterval` です。

`ConversationCollection` には、このメソッドが最後に呼び出されたときに収集された会話の情報が含まれています。

