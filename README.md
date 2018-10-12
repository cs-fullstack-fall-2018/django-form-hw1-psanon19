# django-form-hw1

Watch the video here: https://youtu.be/6oOHlcHkX2U

Below, write out how to create a form in a new views method using any of the classes/models we used today.


  class MovieForm (forms.ModelForm):
    class Meta:
      model = MovieForm
      fields = [
            'name'
            'rating'
            'duration'
    
then in views
  
  def movie_create_view(request):
    form = MovieForm(request.POST or None)
    if form.is_valid():
        form.save()
        form = MovieForm()
    context = {
        'form': form
    }
    return render(request, "MY TEMPLATE ROUTE", context)
