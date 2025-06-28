1.
ffmpeg -i input.mp4 -c copy -map 0 -segment_time 00:05:00 -f segment -reset_timestamps 1 output_%03d.mp4
2. 文件批量操作
```
@echo off
set "output_base=G:\333"
for %%F in (*.mp4) do (
    ffmpeg -i "%%F" -c copy -map 0 -segment_time 00:05:00 -f segment -reset_timestamps 1 "%output_base%\%%~nF_%%03d.mp4"
)
pause
```
