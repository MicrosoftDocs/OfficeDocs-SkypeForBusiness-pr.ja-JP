---
title: 公園を呼び出すし、マイクロソフトのチームで取得
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: チームのクラウド サービスに保留中の通話をパークおよび取得を使用します。
ms.openlocfilehash: 02ec2b3af52cac65f82f5f0f0fc2b4b54ae61369
ms.sourcegitcommit: 5f7e078125f810a9e9a89052854ef63916afe7d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "27283160"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>公園を呼び出すし、マイクロソフトのチームで取得

パークおよび取得は、チームのクラウド サービスに保留中の呼び出しを行うユーザーをできるようにする機能です。 呼び出しが駐機している場合、サービスは、呼び出しを取得するための一意のコードを生成します。 呼び出しまたは他のユーザーを保持しているユーザーは、呼び出しを取得するのにコード、およびサポートされているアプリケーションまたはデバイスを使用できます。 

コール パークを使用するための一般的なシナリオは次のとおりです。 

- 工場で作業しているユーザのための呼び出し必要事項を受付係。 受付係では、パブリック アドレス システムを呼び出し、コード番号を発表します。 ユーザー呼び出しの工場チームの電話を選択し、呼び出しを取得するコードを入力してください。
- デバイスのバッテリの電源が不足しているために、ユーザーの事項をモバイル デバイス上の呼び出し。 ユーザーことができますしを入力し、チームの机上電話からの呼び出しを取得するコードです。
- サポートの代表的な公園顧客は、呼び出しし、呼び出しを取得し、お客様を支援する専門家のチームのチャンネルでお知らせを送信します。 専門家の呼び出しを取得するためにチームのクライアントのコードが入力されます。

> [!IMPORTANT]
> この機能は、配置モードのチームのみで利用可能なだけです。 チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。

## <a name="license-required"></a>ライセンスが必要

駐機し、呼び出しを取得、ユーザーが、エンタープライズ VoIP のユーザーをする必要があり、管理者が、コール パークのポリシーにはユーザーの与える必要があります。 ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。

## <a name="call-park-and-retrieve-feature-availability"></a>公園を呼び出すし、使用可能な機能を取得します。

パークおよび取得は、現在、次のクライアントとデバイスです。 (チームのみのモードで、PSTN への接続の有無にかかわらずサポート)。

| 機能 | チームのデスクトップ | チームの Mac アプリケーション | チームの Web アプリケーション (エッジ) |チーム モバイル iOS と Android アプリ | チームの IP 電話 | ビジネス IP 電話の Skype |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 公園の呼び出し | あり | あり | あり | 準備中 | 準備中| なし |
| 停止の呼び出しを取得します。 | あり | あり | あり | 準備中 | 準備中| なし |
| 取得されていない通話の呼び出しに戻る | あり | あり | あり | 準備中 | 準備中| なし |

## <a name="configuring-call-park-and-retrieve"></a>パークおよび取得を構成します。

コール パークと取得を構成する管理者をする必要があり、機能が既定で無効にします。 ユーザーに対して有効にし、コール パークのポリシーを使用してユーザー グループを作成できます。 一連のユーザーに同じポリシーを適用すると、駐機し、自体の間での呼び出しを取得することがようになります。 ユーザーのコール パークを構成し、コール パークのユーザー グループを作成、以下の手順を実行します。

コール パークを使用し、機能を取得する方法の詳細については、[公園のチームでの呼び出し](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)を参照してください。

### <a name="configure-call-park-and-retrieve-with-powershell"></a>コール パークを構成して、PowerShell を使用して取得

[新規 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)の PowerShell コマンドレットを使用すると、コール パークのポリシーを作成できます。

コール パークのポリシーを付与するのに[Grant CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell コマンドレットを使用します。

## <a name="troubleshooting"></a>トラブルシューティング

ユーザーは、公園を参照してくださいか、ボタンを取得することはできません。 

- パーク ポリシーの有効化をユーザーが持っていることを確認します。 

ユーザーの呼び出しを取得しようとしてくださいが成功しない場合は、以下を確認します。

- ユーザーがチームのクライアントやチームが有効なデバイスと電話を使用していることを確認します。
- グループ – は、ユーザーのコール パークのグループのメンバーですか。
- 島モード – パークおよび取得は、チーム島モードで使用可能ではありません。
- 呼び出しは既に取得または終了します。

## <a name="more-information"></a>詳細情報

[公園チームでの呼び出し](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。