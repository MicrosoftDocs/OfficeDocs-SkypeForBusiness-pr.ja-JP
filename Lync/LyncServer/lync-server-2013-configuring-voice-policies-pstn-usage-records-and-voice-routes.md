---
title: 'Lync Server 2013: 音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成'
TOCTitle: 音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48271456
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成

 

_**トピックの最終更新日:** 2012-10-10_

音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。 音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。 PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。 つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。

新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。

> [!NOTE]
> ユーザー スコープを使用して音声ポリシーを作成し、それを個々のユーザーまたはグループに割り当てることもできます。


これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。

## このセクション中

  - [Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Lync Server 2013 での PSTN 使用法レコードの表示](lync-server-2013-view-pstn-usage-records.md)

  - [Lync Server 2013 での発信通話用のボイス ルートの構成](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Lync Server 2013 での音声ルーティング構成のエクスポートとインポート](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

