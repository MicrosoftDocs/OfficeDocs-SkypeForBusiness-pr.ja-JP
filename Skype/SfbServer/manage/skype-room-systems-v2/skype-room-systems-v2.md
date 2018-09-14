---
title: Skype ルーム システム v2 の管理の概要
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Skype ルーム システム v2 の管理の概要です。
ms.openlocfilehash: d79c04c69e320f404c8ce245120e9b01bd8de1ca
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965657"
---
# <a name="management-overview"></a>管理の概要 

確認して、Skype ルーム システム v2 システム、ユーザーの利用可能な優れた操作を提供する操作が発生しを開発し、継続的なメンテナンスを実行することが重要です。 

## <a name="monitoring"></a>監視 

Skype ルーム システム v2 のシステムの監視は、2 つの主要な活動で構成されます。

-  デバイス、アプリケーション、および周辺機器の監視

-  品質と信頼性の監視 (救難)

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a>Skype ルーム システム v2 のデバイス、アプリケーション、および周辺機器の監視

ユーザーが Skype ルーム システム v2 の単位を使用できることを確認するには、単位は、Skype ルーム システム v2 アプリケーションが正しく構成されてネットワークに接続されている、および、機能している周辺機器に接続するのにする必要があります。 


Skype ルーム システム v2 のアプリケーションと接続されている周辺機器の状態についての情報は、Skype ルーム システム v2 のアプリケーションによって Windows イベント ログに書き込まれ、[この資料に](oms.md#understand-the-log-entries)記載されています。 

|**設定**|**により、**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows 探して AutoAdminLogon = (dword) 1  <br/> |起動するように Skype ルーム システム v2 を有効に  <br/> |
|電源管理 -\> AC、画面をオフに 10 分後  <br/> 電源管理 -\> Ac システムをスリープ状態を配置しません。  <br/> |により、接続されている表示をオフにして、自動的に復帰する Skype ルーム システム v2  <br/> |
|net accounts /maxpwage:unlimited  <br/> または、ローカル アカウントでパスワードの期限切れを無効にする同等の手段。この設定に失敗すると、パスワードの期限が切れていることが通知され、Skype アカウントのログオンが失敗する原因になります。この影響はマシン上のすべてのローカル アカウントに及びます。したがって、この設定に失敗すると、ボックスの管理アカウントも最終的には期限切れになります。  <br/> |常にログインするように Skype アカウントを有効にする  <br/> |
   
グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)で説明します。
  
## <a name="remote-management-using-powershell"></a>PowerShell を使用したリモート管理
<a name="RemotePS"> </a>


Skype ルーム システム v2 システムを監視する Microsoft オペレーション マネージャーのスイートを使用することをお勧めします。 監視と警告の基本的なセットアップ方法については、 [OMS を使用して Skype ルーム システムの展開 v2 の管理](../../deploy/deploy-clients/with-oms.md)を参照してください。 

このガイドを使用すると、Skype ルーム システム v2 の単位数と、配置での問題を識別する簡単に使用できるダッシュ ボードを作成できます。 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/>意思決定ポイント|<ul><li>Skype ルーム システム v2 の展開を監視する操作の管理スイートを使用することを確認します。</li><li>メール ・ アラートを使用するターゲットの配布リストを決定します。</li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>品質と信頼性の監視方法を定義します。</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>品質と信頼性の監視 (救難)

懸念される領域を識別し、解決に向けて、継続的なオペレーションの品質と信頼性の呼び出し、会議の品質と信頼性、トレンドを監視するのには、展開の一部としてプロシージャを監視を実装することをお勧めします。 

救難に、建物の情報をアップロードするとき簡単に建物を比較し、特定の問題を絞り込んで、建物ごとのレベルでの呼び出しの品質と信頼性の傾向を調査できます。 詳細については、 [Skype のオンライン配信のビジネスおよび運用ガイド 』 のモニター ・救難](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15)をダウンロードします。 

確認し、することと[品質の経験をレビュー ガイド](https://aka.ms/qerguide)の品質と信頼性の傾向を把握するのには、次の解決するためのアクション ・ プランの作成をお勧めします。 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a>Skype ルーム システム v2 の OS と Skype ルーム システムのアプリケーションを更新 

Skype ルーム システム v2 OS と Skype ルーム システム v2 アプリケーション製品の更新プログラムと機能強化の恩恵を更新することをお勧めします。 詳細については、 [Skype ルームの管理のシステムのバージョン 2](room-systems-v2-operations.md#software-updates)を参照してください。 

## <a name="troubleshooting"></a>トラブルシューティング

オペレーション管理スイートが、運用チームとヘルプデスク警告が表示されます、Skype ルーム システム v2 の問題にするために、上記のセクションで説明したように警告を設定することをお勧めします。 [PowerShell を使用してリモート管理](room-systems-v2-operations.md#remote-management-using-powershell)では、PowerShell のリモート管理に使用できるオプションが説明されています。 周辺機器が切断されているローカルの「スマート手」かを調査し、デバイスを再接続する IT サポートに依存する必要があります。 

トラブルシューティングと管理モードの詳細については、 [Skype ルームの管理のシステムのバージョン 2](room-systems-v2-operations.md#admin-mode-and-device-management)を参照してください。 

## <a name="see-also"></a>関連項目

[Skype ルーム システムのバージョン 2 のヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Skype Room Systems バージョン 2 の計画](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[Skype Room System バージョン 2 を展開する](../../deploy/deploy-clients/room-systems-v2.md)

[Skype Room Systems バージョン 2 コンソールを構成する](../../deploy/deploy-clients/console.md)

[Skype Room Systems バージョン 2 のコンソールの設定を、XML 構成ファイルを使用してリモートで管理する](xml-config-file.md)
