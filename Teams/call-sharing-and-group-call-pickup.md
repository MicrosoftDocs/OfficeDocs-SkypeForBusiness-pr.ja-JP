---
title: Microsoft Teams での通話の共有およびグループ通話ピックアップ
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 共有を呼び出すし、グループ通話ピックアップできるように、ユーザーが利用できない場合、呼び出しをキャプチャできるように、着信呼び出しを同僚と共有します。
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211824"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Microsoft Teams での通話の共有およびグループ通話ピックアップ

呼び出しの共有とグループは、着信呼び出しの合計の仕事仲間の仕事仲間は、ユーザーが使用できない時に発生する呼び出しに応答できるように、マイクロソフトのチームがユーザーの共有の機能をピックアップを呼び出します。

グループ コール ピックアップは他の形式のユーザーが共有経由でオーディオとビジュアルの通知、ビジュアルだけでは、着信の通知が必要な方法を構成することができますので、着信の転送または同時呼び出し) などの共有の呼び出しよりも受信者を妨げずやバナーのチームのアプリケーションで)、および、それに応答するかどうかを決定することができます。

呼び出しを他のユーザーと共有する、するには、ユーザーが呼び出しのグループを作成しでその呼び出しを共有するユーザーを追加します。 同時呼び出しを選択するか、設定を転送します。 詳細については、[チームでの転送と同時の呼び出し音を呼び出す](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)を参照してください。

> [!IMPORTANT]
> ユーザー、グループの所有者を呼び出し、および呼び出しのグループのメンバーは、展開モードではチームだけである必要があります。 チームの展開方法の詳細については、[マイクロソフト チームの理解と Skype ビジネスの共存と相互運用性を](teams-and-skypeforbusiness-coexistence-and-interoperability.md)参照してください。

## <a name="license-required"></a>ライセンスが必要

ユーザーを設定し、呼び出しの共有を使用し、コール ピックアップをグループ化するを有効にするエンタープライズ VoIP をする必要があります。 ライセンス ・ モデルの詳細については、 [Office 365 は、マイクロソフトのチームのライセンス](office-365-licensing.md)を参照してください。

## <a name="configure-group-call-pickup"></a>グループ コール ピックアップを設定します。

コール ピックアップのグループを設定するにユーザーは最初の呼び出しグループ (これは、同じセキュリティ グループ、または、Office 365 のグループとして) を構成しでその呼び出しを共有するユーザーを追加し。 同時呼び出しを選択する、転送の設定を呼び出すか。 詳細な情報および詳細な手順についてを参照してください[チームに転送し、同時のリングを呼び出します](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。

グループの作成と通知の設定は、ユーザー ・ ベースの機能を呼び出す管理者は、ユーザーに対してこれらの機能を構成するのにはありません。 セキュリティ グループまたはグループを Office 365 からの呼び出しのグループを作成できません。これらは、チームで作成する必要があります。

管理者は、ユーザーの**TeamsCallingPolicy の AllowCallGroups**設定を使用して呼び出しのグループを有効にする必要があります。 管理者は、このユーザーが呼び出しのグループを構成できるかどうかを制御することができますだけ。 True の場合、管理者に設定すると、ビットを設定して、任意のユーザーをグループ化する呼び出しを追加することからユーザーを防ぐことはできません。

## <a name="limitations"></a>制限

テナントには、最大 32,768 の呼び出しのグループを含めることができます。 最大 5 ユーザーが各呼び出しのグループのことができます。 

## <a name="more-information"></a>詳細情報

[着信の転送およびチームでの同時呼び出し](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)