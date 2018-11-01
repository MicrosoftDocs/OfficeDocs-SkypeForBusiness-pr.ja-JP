---
title: モビリティ サービスおよび UCWA の使用状況の監視
TOCTitle: モビリティ サービスおよび UCWA の使用状況の監視
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48272692
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# モビリティ サービスおよび UCWA の使用状況の監視

 

_**トピックの最終更新日:** 2013-02-14_

Lync Server Mobility Service (Mcx) と Unified Communications Web API (UCWA) で使用される CPU とメモリを継続的に監視する必要があります。使用状況を監視するには、次を使用できます。

**For Unified Communications Web API (UCWA):**

  - インターネット インフォメーション サービス (IIS) マネージャー内の **LyncUcwa** ワーカー プロセス。\[**ワーカー プロセス**\] ウィンドウで、\[**CPU %**\] および \[**プライベート バイト (KB)**\] (メモリ) の列を確認します。

  - \[**CPU**\] および \[**プロセッサ**\] パフォーマンス カウンター

ほとんどの展開で、UCWA の CPU 使用率は平均で 15% を下回っている必要があります。メモリ使用量は、「[サーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)」で説明されている制限の範囲内に含まれる必要があります。

CPU とメモリの使用状況カウンターに加えて、以下のパフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。

  - **LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**。これは、サーバー上の保留中の Web 要求数を示します。このカウンターが 10,000 に達すると、以降の要求は失敗し、エラー メッセージ "503 - サービスを利用できません" が表示されます。

  - **ASP.NET\\Requests Queued** (常にゼロである必要があります)。

> [!NOTE]
> これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。


**Mobility Service (Mcx):**

  - インターネット インフォメーション サービス (IIS) マネージャー内の **CSIntMcxAppPool** および **CSExtMcxAppPool** ワーカー プロセス。\[**ワーカー プロセス**\] ウィンドウで、\[**CPU %**\] および \[**プライベート バイト (KB)**\] (メモリ) の列を確認します。

  - \[**CPU**\] および \[**プロセッサ**\] パフォーマンス カウンター

ほとんどの展開で、Mobility Service の CPU 使用率は平均で 15% を下回っている必要があります。メモリ使用量は、「[サーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)」で説明されている制限の範囲内に含まれる必要があります。

CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。

  - **ASP.NET v2.0.50727\\Requests Current**。これは、サーバー上の保留中の Web 要求数を示します。このカウンターが 5,000 に達すると、以降の要求は失敗し、エラー メッセージ "503 - サービスを利用できません" が表示されます。

  - **ASP.NET\\Requests Queued** (常にゼロである必要があります)。

> [!NOTE]
> これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。


## 関連項目

#### 概念

[サーバーのメモリ容量制限の監視](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

