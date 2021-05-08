---
title: Microsoft Teams のユーザー エクスペリエンスを計画する
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: クライアント Teamsを選択し、エンドポイントの品質を計画し、エンドポイントをデプロイし、オーディオ デバイスWi-Fi推奨事項を取得します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094735"
---
# <a name="plan-my-users-experience"></a>ユーザーエクスペリエンスを計画する

この記事では、ユーザーのエクスペリエンスに直接影響するクラウド 音声サービス デプロイの要素を適切に識別するための要件の概要を説明します。 デプロイ前にこれらの項目を準備することで、ユーザーに高品質で信頼性の高いエクスペリエンスを正常に提供する可能性を高めるでしょう。 

## <a name="client-deployment"></a>クライアントのデプロイ

Microsoft Teams、Web、デスクトップ (Windows Mac)、モバイル (Android および iOS) で使用できるクライアントがあります。 デスクトップ (Windows および Mac) とモバイル クライアントのインストール方法の詳細については、「Get clients for Microsoft Teams 」[を参照してください](./get-clients.md)。

## <a name="client-updates"></a>クライアントの更新

この機能の主な利点Teams、クライアントは自動的に最新の状態に維持されます。 PC と Mac 上のクライアントは、アプリがアイドル状態のときに新しいビルドがあるかを確認したり、新しいクライアントをダウンロードしたりする、バックグラウンド プロセスを使用して更新されます。

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>エンドポイント品質の計画

次の図に示す通り、エンドポイントは、ユーザーに高品質のエクスペリエンスを提供する上で重要なブロックです。

![品質にかかわる 3 つの構成要素を取り上げた図](media/plan-my-users-experience-image1.png "品質の 3 つのコンポーネントと、サービス管理が 3 つのコンポーネントすべてとどのように重なるかについて説明する図。エンドポイントに重点を置く。")

Teamsエンドポイントは、PC、Mac、タブレット、モバイル デバイスなど、多くのデバイスで実行できます。 エクスペリエンスの一部には、デバイスだけでなく、ユーザーがデバイスに接続する方法 (たとえば、デバイスの組み込みのマイク/スピーカー、イヤーパッド、最適化されたヘッドセットを使用する方法) が含されます。 最適化されたヘッドセットを使用すると、全体的なユーザー エクスペリエンスが向上します。

エンドポイントの計画についての次のガイダンスは、自分の組織が正常に Teams を使い始められるようになるために役立つ情報を提供します。

## <a name="endpoint-capability"></a>エンドポイントの機能

計画の最初の部分は、組織内のすべての PC と他のデバイスが、すべてのデバイスで実行Teams。 これには、単にハードウェア要件を確認するだけではなく、PC がバックグラウンドで他に何を実行しているかを理解することも含まれます。 多くの組織は、侵入検出システムやマルウェア対策ソフトウェアなどの、デバイスの基本パフォーマンスに影響する可能性がある、他のソフトウェアを実行しています。

各プラットフォーム (Web、デスクトップ、モバイル) 上の Teams クライアントのソフトウェア要件については、「Get [clients for Microsoft Teams](./get-clients.md)」を参照してください。

## <a name="endpoint-firewalls"></a>エンドポイントのファイアウォール

クライアント側のファイアウォールはユーザー エクスペリエンスに大きな影響をおよぼす可能性があります。
クライアント側のファイアウォールは、通話が確立されないようにするだけではなく、通話品質に影響する可能性があります。 クライアント ファイアウォールで適切な除外を構成します。クライアント ファイアウォールの URL と IP アドレスMicrosoft 365またはOffice 365[の情報に基づいて行います](/microsoft-365/enterprise/urls-and-ip-address-ranges)。 ご利用のサードパーティ ベンダーには、例外の作成方法についての固有のガイダンスがあります。

>[!NOTE]
> Microsoft Teams は、適切なファイアウォール構成で自動的に Windows ファイアウォールを更新します。

## <a name="wi-fi-recommendations-for-endpoints"></a>エンドポイント向けの Wi-Fi の推奨事項

最適化されたネットワークをデプロイし、Wi-Fiのリアルタイム ワークロードをサポートするには、重要な計画がMicrosoft Teams。 次のセクションでは、エンドポイントを計画するときによくある落とし穴を回避するために役立つ一般的なガイダンスを示します。

### <a name="wi-fi-drivers"></a>Wi-Fi ドライバー

一部Wi-Fiドライバーが問題になる可能性があります。 たとえば、ドライバーによりアクセス ポイント間で非常に積極的なローミング動作が行われる場合があり、その結果として通話品質が下がります。
これは一般的な問題ではありません。ただし、PC 上の Wi-Fi ドライバーが更新され、展開前にテスト済みである必要があります。

### <a name="wi-fi-bands"></a>Wi-Fi バンド

現在の Wi-Fi 機器では、2.4 GHz と 5.0 GHz という 2 つの主な種類のバンドが使用されています。 自分の組織が両方のバンドを提供している場合、ドライバーの設定を、5.0 GHz バンドを優先するように構成する必要があります。 このバンドでは、スループットの点で密度がより高く、2.4 GHz バンドで生じる干渉による影響がより少なくなります。
この推奨事項は、5.0 GHz のネットワーク バンドを正しく最適化したことを想定しています。

### <a name="wi-fi-radio-type"></a>Wi-Fi 無線タイプ

新しい Wi-Fi 無線タイプをサポートするデバイス向けの計画です。 プロビジョニングしたデバイス上で 802.11ac またはより新しいタイプを利用すると、優れた Wi-Fi パフォーマンスを得ることができます。

### <a name="wireless-avoidance"></a>ワイヤレス回避

組織によっては、Wi-Fi を完全に回避することを希望します。 このガイダンスは、有線ネットワークに直接接続するユーザーに対する推奨事項として提供されることがあります。 場合によっては、PC が優先接続に接続されていても、ネットワークのバインド順でワイヤレス接続が優先されているため、その無線接続を継続して使用することがあります。 このような意図しない動作を回避するには、このシナリオを回避するようにバインド順を構成します。

### <a name="80211-power-save-protocol"></a>802.11 Power Save プロトコル

組織で 802.11 Power Save プロトコルをサポートしないワイヤレス アクセス ポイントまたはルーターを使用している場合は、Windows デバイスで実行されている Microsoft Teams で通話の低下や低品質が発生する可能性があります。 ワイヤレス アクセス ポイントまたはルーターをアップグレードすることができない場合は、バッテリで動作しているデバイスで Windows 電源プラン設定を更新する必要があります。 より詳細な情報と、構成についてのガイダンスは次の[サポート記事](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)で提供されています。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>組織Teamsどのクライアントをデプロイしますか。</li><li>ユーザーに対して最初にTeamsクライアントをデプロイする方法</li><li>Whoエクスペリエンスの要件を満たしていることを検証するために、エンドポイントとデバイスTeams評価する責任がありますか。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>クライアントにデプロイするプロセスを文書化Teamsします。</li><li>エンドポイントとデバイスを評価し、実行と修復が必要です。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Teams 用のデバイス

Microsoft Teams は会議のために、または電話システムとして使用することができます。 これらの機能を使用するとき、Teams のために使用されるインターフェイス デバイスは、ユーザー エクスペリエンスにおいて重要な役割を果たします。

内蔵の PC スピーカーとマイクを使用する構成で、ユーザーが許容できる音質が得られる場合があります。 ただし、通常、これらのデバイスはノイズ 除去用に最適化されていないので、どの種類の環境ノイズでも、他のデバイスが呼び出しにダウンストリームに影響を与える可能性があります。 このようなシナリオに最適化されたデバイスを利用すると、高品質のエクスぺリエンスを確保することができるようになります。

各デバイスが、自分のユーザーのニーズに合う必要があります。 ヘッドセットなどのデバイスを組織内のそれぞれの人やユース ケースに合わせて調整する必要があります。
人からデバイスへのマッピングの実施を、計画プロセスの一部として完了している必要があります。

デバイスを選択したら、それらを最終検証のパイロット テスト計画に含めます。 パイロット中にアンケートを活用して、デバイス戦略が適正であることを確認するために、フィードバックを収集します。

> [!NOTE]
> 現時点では、Skype for Business の認証プログラムを通して認証されたオーディオ デバイスを使用することをお勧めします。 このプログラムで認定されているデバイスを見つけるには、「Microsoft Teams [USB](https://products.office.com/microsoft-teams/across-devices/devices)オーディオ デバイスとビデオ デバイス」[を参照してください](/SkypeForBusiness/certification/devices-usb-devices)。



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>ユーザーエクスペリエンスと会議室エクスペリエンスに関する組織の全体的なデバイス戦略を決定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>組織のペルシャ対デバイス マッピングの演習を完了します。</li><li>ユーザーと会議室のデバイスを取得するプロセスを文書化します。</li><li>ユーザーと会議室のデバイスを展開および構成するプロセスを文書化します。</li><li>初期デバイスを調達してデプロイを開始します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->