# AGENTIC-AI
Agentic AI PoC for "Knowledge Summarizer for Professionals", ideal for automating your daily info-digest and saving time.
if __name__ == "__main__":

print("[INFO] Starting Digest Generation...")


email_summary = fetch_and_summarize_emails()

slack_summary = fetch_and_summarize_slack()

news_summary = fetch_and_summarize_news()

recent_digests = get_recent_digests()


final_digest = compile_digest(

email_summary=email_summary,

slack_summary=slack_summary,

news_summary=news_summary,

memory_logs=recent_digests

)


store_digest(final_digest)

print("[SUCCESS] Digest Created and Stored Successfully.")



# agents/email_agent.py

import os

import base64

from google.oauth2 import service_account

from googleapiclient.discovery import build

from openai import OpenAI
